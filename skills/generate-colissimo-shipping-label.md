---
name: generate-colissimo-shipping-label
description: Validate and generate a Colissimo shipping label (with CN23 customs declaration for international parcels) through the SLS REST API.
api: colissimo:colissimo-sls-api
operations:
- generateToken_1
- checkGenerateLabel_1
- generateLabel_1
- generateCN23_1
generated: '2026-10-13'
method: generated
source: openapi/colissimo-sls-openapi.yml
---

# Generate a Colissimo shipping label

Grounded in the SLS REST contract served at https://ws.colissimo.fr/sls-ws/SlsServiceWSRest/2.0/openapi.json.

1. Optionally obtain a session token with `generateToken_1` (POST /generateToken) using your Colissimo contract credentials.
2. Validate the shipment payload with `checkGenerateLabel_1` (POST /checkGenerateLabel) and fix any returned error codes.
3. Create the label with `generateLabel_1` (POST /generateLabel); the response carries the parcel number and label document.
4. For shipments outside the EU customs territory, produce the customs form with `generateCN23_1` (POST /generateCN23).

Credentials are Colissimo business-contract credentials issued to Colissimo Entreprise customers; never log them.
