# QA documentation sample — API repeated-read regression

Prepared for Roman Neklyudov's QA portfolio, 21 September 2026. AI-assisted documentation based on an inspected public code change. This is a test-suite defect in a demonstration project, not a production payment incident.

## Bug report: repeated-read check performs only one request

**Component:** Postman collection, Idempotency folder.
**Suggested severity:** Medium — false confidence in test coverage; no demonstrated production loss.
**Status:** Fix proposed in [PR #1](https://github.com/r0meo-1/api-automation-tests/pull/1); merge and deployment are not claimed.
**Reviewed fix:** `2701f79b03461205bb00aa840b874a10f46e2494`.

**Preconditions:** Original collection from the PR's base revision; Newman; an isolated HTTP stub for `/posts/2`. First response: HTTP 200 with `{ "id": 2, "title": "same" }`. Configure a potential second response with the same ID and a changed title.

**Steps:**

1. Run only the collection's Idempotency folder against the stub.
2. Count incoming requests.
3. Inspect the collection assertions and run result.

**Actual behavior in the original implementation:** One request is sent. Assertions verify HTTP 200 and `id == 2`; there is no second response comparison. The changed second response cannot be observed.

**Expected behavior:** Two independent GET requests are sent. Both must succeed and their complete JSON bodies must match for this static resource. A changed body, HTTP error or disconnected second request must fail the collection.

**Evidence:** The [PR diff](https://github.com/r0meo-1/api-automation-tests/pull/1/files) shows the original single-response assertion and the added second request. It also includes a local HTTP test harness that counts requests and covers four modes. The PR records [CI run 35608857022](https://github.com/r0meo-1/api-automation-tests/actions/runs/35608857022). This document was prepared from source review; it does not claim a new local test execution today.

## Test case: detect a changed second response

**ID:** API-REPEAT-02
**Purpose:** Ensure a stable resource identifier cannot hide a changed response body.
**Test data:** First body `{ "id": 2, "userId": 1, "title": "same", "body": "text" }`; second body differs only in `title`, set to `changed`. Both return HTTP 200.

| Step | Expected result |
|---|---|
| Start the local stub in `changed` mode and run the Idempotency folder against it | Exactly two GET requests reach `/posts/2` |
| Inspect the second-request status assertion | Passes: the response is HTTP 200 |
| Inspect the full-body comparison | Fails because the title changed |
| Inspect the regression harness | Passes because it expects the collection to detect this deliberately broken scenario |

The distinction in the final two rows matters: a regression harness may pass when the tested collection correctly fails.

## Focused regression checklist

- [ ] Stable responses: two requests, no collection assertion failures.
- [ ] Changed title with unchanged ID: two requests, collection failure.
- [ ] HTTP 500 on the second request: collection failure.
- [ ] Second connection closed without a response: collection failure.
- [ ] Stub closes after every case, including failures.
- [ ] No production credentials or payment endpoints used.

Unchecked boxes are a reusable execution template, not a report of a completed run.

## Interview explanation

The original check tested a property of one response, although its name promised repeated reads. The fix makes the required second request and compares the whole body. Controlled failures demonstrate that the check can detect defects, while the stable case checks that valid behavior still passes.

This does not prove payment idempotency, booking persistence or consistency of an API whose resource is expected to change. A real payment test needs a payment-specific contract, isolated test data, a sandbox and assertions on the number and state of created transactions.
