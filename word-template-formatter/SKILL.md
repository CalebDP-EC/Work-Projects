---
name: word-template-formatter
description: Create Microsoft Word documents by cloning one canonical template and filling it with content. Use when generating or rewriting .docx files, especially as-built documents, so the output must preserve the template exactly while becoming a new finished document.
---

# Word Template Formatter

## Workflow

1. Treat `assets/template.docx` as the source of truth.
2. Before starting document creation, ask for:
   - Customer Name
   - Customer Logo
3. If no customer logo is provided, keep going and use the template's customer-logo placeholder.
4. If relevant screenshots exist in the chat history, include them in the document near the related content.
5. Create a new working copy of the template and fill that copy with the document content.
6. Preserve the template exactly: layout, styles, page setup, headers/footers, numbering, images, section breaks, front page, table of contents, and page furniture.
7. Do not clear the document body, rebuild the front page, or remove template paragraphs/tables unless the template itself instructs that a placeholder must be replaced.
8. Use the template copy as the finished document. Do not re-style the source document to imitate the template.
9. Make the smallest content edit that satisfies the request.
10. If the template file is missing, stop and ask for it before formatting the document.

## Formatting Rules

- Do not invent fonts, colors, spacing, margins, or headings that are not already in the template.
- Keep all visible formatting aligned to the template, including page headers, footers and section breaks.
- Keep all images and decorative page-corner artwork from the template in the exact same position and size, unless the request explicitly asks for changes.
- Preserve existing placeholder positions and replace only the content that needs to change.
- When a document conflicts with the template, the template wins always.
- If the request is to reformat a document, do not change the content unless it is necessary to fill the template copy correctly.
- For as-built requests, produce a new DOCX based on the template and treat that copied file as the deliverable.
- Never remove the template's existing title page, contents page, footers, headers, logos, shapes, or table of contents.

## Output Check

Before finishing, verify that the document still matches the template structure and that no manual formatting drift was introduced.

## Resources (optional)

### scripts/
Not required.

### references/
Not required.

### assets/
Place the canonical Word template at `assets/template.docx`.
