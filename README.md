# Anuvadini MagicEye OCR

> This repository contains documentation only — no code and no weights.

MagicEye is Anuvadini's document vision-language model for OCR and document understanding across the 22 scheduled Indian languages and English. It is trained by Anuvadini and runs in production on Anuvadini's on-premises GPU servers.

## Architecture
| Item | Value |
|---|---|
| Parameters | **686,154,304** |
| Precision | bfloat16 (weights 1.37 GB) |
| Image encoder | 12 layers, width 768, 12 heads, patch size 16 |
| Text decoder | 24 layers (18 linear-attention + 6 full-attention), width 1,024, 8 query / 2 key-value heads, feed-forward 3,584 |
| Vocabulary | 65,425 |

## Capabilities
- Printed text, handwriting, historical manuscripts, scanned archives, government bulletins, financial documents, textbooks and newspapers
- Complex tables with nested and multi-level headers; charts and infographics; reading order in multi-column layouts
- Structured Markdown, JSON or plain-text output; visual question answering over documents
- Evidence-based acceptance: the PDF text layer is used first, low-confidence regions are re-read, unverifiable readings are routed to a person

## Deployment
Docker / OCI container with REST API; on-premise and air-gapped. Production throughput measured at ≈ 210 documents per minute using half of one A100 80 GB GPU.

---
© Anuvadini Foundation. All rights reserved. Documentation only.
