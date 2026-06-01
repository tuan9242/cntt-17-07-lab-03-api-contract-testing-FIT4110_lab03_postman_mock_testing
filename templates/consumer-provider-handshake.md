# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 2026-06-02
- Provider team: team-iot
- Consumer team: team-analytics
- Provider service: IoT Ingestion Service
- Consumer service: Analytics Service

## Contract

- Contract file: contracts/iot-ingestion.openapi.yaml
- Mock base URL: http://localhost:4010
- Auth method: Bearer token
- Endpoint được test: GET /readings

## Smoke test

### Request

```http
GET /readings
Authorization: Bearer lab-token
Content-Type: application/json
```

### Expected response

```json
{
  "readings": [
    {
      "readingId": "urn:uuid:fca3508b-9d41-4770-bc4a-9f5cf3f11c7b",
      "deviceId": "device-001",
      "timestamp": "2026-06-02T00:00:00Z",
      "metric": "temperature",
      "value": 25.5,
      "unit": "celsius"
    }
  ]
}
```

## Kết quả

- [x] Consumer gọi mock thành công.
- [x] Consumer parse được field cần dùng.
- [x] Consumer hiểu lỗi 4xx/5xx provider trả về.
- [x] Có Newman report hoặc screenshot.

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
|---|---|---|---|
| Không có thay đổi | - | - | team-analytics & team-iot |

## Xác nhận

- Provider representative: team-iot representative
- Consumer representative: team-analytics representative
