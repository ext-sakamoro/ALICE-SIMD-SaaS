# ALICE-SIMD SaaS

SIMD fast-math primitives API (RMSNorm, Softmax, etc.)

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-SIMD |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/rmsnorm` | RMSNorm正規化 |
| `POST /api/v1/softmax` | Softmax計算 |
| `POST /api/v1/batch_fma` | バッチFMA演算 |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
