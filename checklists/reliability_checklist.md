# Reliability Checklist - FIT4110 Lab 03

Completed for `team-iot` / IoT Ingestion contract tests.

## 1. Functional tests

- [x] Co test cho endpoint health.
- [x] Co test happy path cho endpoint chinh.
- [x] Co kiem tra status code 2xx.
- [x] Co kiem tra field quan trong trong response.
- [x] Co it nhat 1 test doc du lieu danh sach hoac chi tiet.

## 2. Auth tests

- [x] Co test thieu token.
- [x] Co test sai token hoac token rong.
- [x] Endpoint public duoc khai bao ro neu khong can auth (`GET /health` co `security: []`).
- [x] Test the hien dung expected status 401/403 tren local service; mock duoc skip co ghi chu vi Prism khong validate auth that.

## 3. Negative tests

- [x] Co test thieu field bat buoc.
- [x] Co test sai kieu du lieu.
- [x] Co test sai enum hoac gia tri ngoai mien.
- [x] Loi tra ve theo cung mot error model `ProblemDetails`.

## 4. Boundary tests

- [x] Co test min/max hoac du lieu sat nguong (`value=80`, `value=81`).
- [x] Co test limit/pagination cho endpoint danh sach (`limit=101`).
- [x] Co test metadata/tham so khong hop le qua negative payload va query validation.
- [x] Co ghi chu ky vong xu ly du lieu bien trong test-case matrix.

## 5. Reliability tests co ban

- [x] Co kiem tra response time cho local service.
- [x] Timeout mong muon: Newman/CI cho mock server san sang trong 30 giay bang `wait-on`.
- [x] Co ghi chu rate limit/idempotency phu hop qua response `429 Too Many Requests`.
- [x] Co consumer-side smoke test voi AI Vision mock.

## 6. Evidence

- [x] Collection export JSON.
- [x] Environment mock export JSON.
- [x] Environment local export JSON.
- [x] Newman report XML/HTML.
- [x] Test-case matrix da dien.
- [x] Bien ban handshake da dien.
