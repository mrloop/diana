# Permanent QR Code Plan

## Goal

Create a QR code for Calum that links to a small web page about Diana.

The aim is not to create a guaranteed permanent URL. No URL can honestly be
guaranteed for 100+ years. The aim is to make the content and the route to it
as durable as practical, with no normal renewals and with enough fallback
information printed alongside the QR code that future recovery is still
possible.

## Current Archive

The self-contained `index.html` was uploaded to Arweave on 2026-05-14.

Web page / QR target:

```text
https://arweave.net/lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8
```

Arweave transaction ID:

```text
lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8
```

No ARK has been minted yet. If a real ARK is added later, point the ARK target
at the Arweave gateway URL above and keep the Arweave transaction ID printed as
fallback text.

Recommended fallback text to print near the QR code:

```text
Diana Buchanan archive page
https://arweave.net/lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8

Arweave transaction ID:
lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8

If this link stops working, search for an Arweave gateway and open this
transaction ID.
```

## Recommended Setup

Use this if a genuine ARK can be minted through an ARK provider or steward:

```text
QR code -> https://n2t.net/ark:/NAAN/name
ARK target -> Arweave gateway URL
Arweave TX_ID -> immutable content identifier
```

In plain terms:

1. Build one self-contained `index.html`.
2. Upload that file once to Arweave.
3. Save the Arweave transaction ID (`TX_ID`).
4. Mint/register an ARK.
5. Point the ARK target at an Arweave gateway URL for the `TX_ID`.
6. Put the `https://n2t.net/ark:/...` URL in the QR code.
7. Print the ARK and the Arweave `TX_ID` as human-readable fallback text.

This gives three useful layers:

- Arweave stores the actual content immutably.
- The Arweave `TX_ID` identifies the content directly.
- The ARK gives a stable public identifier whose target can be updated if
  gateway URLs or access methods change.

## Important Caveat About n2t.net

Use `n2t.net` only for a real registered identifier.

`n2t.net` is a resolver, not a hosting service. It redirects a known identifier
to a stored target URL. It is appropriate for a QR code target if the ARK has
actually been minted and N2T knows how to resolve it.

Do not invent an `ark:/...` URL and assume `n2t.net` will make it work.

## If an ARK Is Not Practical

If a genuine ARK cannot be obtained, use the Arweave gateway URL directly in the
QR code:

```text
https://arweave.net/TX_ID
```

Also print this fallback text near the QR code:

```text
Archived page: Arweave transaction TX_ID
If this link stops working, search for an Arweave gateway and open TX_ID.
```

This is less elegant than ARK -> Arweave, but it is honest and still durable:
the content is addressed by its Arweave transaction ID rather than by a domain
that I personally control.

## What To Print

Do not rely on the QR code alone. Print enough information that a person can
recover the page even if the QR code target stops resolving.

Preferred text if using ARK:

```text
Web page:
https://n2t.net/ark:/NAAN/name

Archived copy:
Arweave TX_ID: TX_ID
```

Fallback text if using Arweave directly:

```text
Web page:
https://arweave.net/TX_ID

Archived copy:
Arweave TX_ID: TX_ID
```

## Website Format

Make the page a single static HTML file:

- Inline CSS.
- No JavaScript unless there is a strong reason.
- Embedded images as `data:` URLs.
- No external fonts, analytics, build assets, or CDN dependencies.
- Include the citation details for the original article.
- Include a short retrieval note explaining the ARK and/or Arweave `TX_ID`.

For this project, the archival `index.html` embeds the page images directly as
`data:` URLs. This avoids future breakage caused by missing image files. Keep
`index-no-embed.html` as the editable source version with normal image links.

## Updates

Arweave content is immutable. Updating means publishing a new version:

1. Create a new `index.html`.
2. Upload it to Arweave.
3. Save the new `TX_ID`.
4. Update the ARK target to the new gateway URL, if using an ARK.

Old Arweave versions should remain accessible by their original transaction
IDs.

## OCR

Mistral OCR is a reasonable option for extracting text from the newspaper
image:

```text
https://mistral.ai/news/mistral-ocr-3
```

For the final page, keep the original scan/image as evidence and include a
clean text transcription for readability.

## Information Needed

Before building the page, collect:

- The best available original image or scan.
- Newspaper name.
- Publication date.
- Section name, if known.
- Page number, column, or paragraph reference, if known.
- Exact text to appear on the page.
- Any short biographical context about Diana that should sit alongside the
  article.
- Where the QR code will physically appear.

## Current Recommendation

Best case:

```text
n2t.net ARK URL in the QR code
Arweave TX_ID printed nearby
Self-contained HTML stored on Arweave
```

Current direct-Arweave setup:

```text
https://arweave.net/lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8 in the QR code
lXWJivu7s_G7s_n8SZKI_9QdZ8Xb9Amix-S1HsM5tU8 printed nearby
Self-contained HTML stored on Arweave
```

This is a strong best-effort archival setup. It should not be described as
guaranteed permanent, but it avoids the biggest failure modes: annual hosting
renewals, domain expiry, missing asset files, and dependence on a single
personal account.

## Sources Checked

- ARK Alliance FAQ: https://arks.org/about/ark-faq-en/
- N2T API documentation: https://n2t.net/e/n2t_apidoc.html
- N2T resolver: https://n2t.net/
- Arweave: https://www.arweave.com/
- Mistral OCR: https://mistral.ai/news/mistral-ocr-3
