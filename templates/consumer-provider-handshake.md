# Consumer-Provider Handshake

## Thong tin chung

- Lab: FIT4110 Lab 03
- Ngay: 2026-05-26
- Provider team: team-vision
- Consumer team: team-iot
- Provider service: AI Vision
- Consumer service: IoT Ingestion

## Contract

- Contract file: `contracts/ai-vision.openapi.yaml`
- Mock base URL: `{{aiVisionMockUrl}}` (`http://localhost:4011` in mock/local environments)
- Auth method: Bearer token via `Authorization: Bearer {{authToken}}`
- Endpoint duoc test: `POST /detect`

## Smoke test

### Request

```http
POST /detect
Authorization: Bearer <token>
Content-Type: application/json
```

```json
{
  "camera_id": "CAM01",
  "image_url": "https://example.com/frame.jpg"
}
```

### Expected response

```json
{
  "detection_id": "DET001",
  "camera_id": "CAM01",
  "label": "person",
  "confidence": 0.91,
  "risk_level": "medium"
}
```

## Ket qua

- [x] Consumer goi mock thanh cong.
- [x] Consumer parse duoc field can dung: `detection_id`, `label`, `confidence`.
- [x] Consumer hieu loi 4xx/5xx provider tra ve thong qua `ProblemDetails` trong contract AI Vision.
- [x] Co Newman report trong `reports/`.

## Ghi chu thay doi hop dong

| Noi dung | Truoc | Sau | Nguoi dong y |
|---|---|---|---|
| Initial Lab 03 smoke contract | N/A | `POST /detect` returns detection result with confidence in `[0,1]` | team-iot, team-vision |

## Xac nhan

- Provider representative: team-vision representative
- Consumer representative: team-iot representative
