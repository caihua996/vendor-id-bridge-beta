# Vendor ID Bridge — public beta

A small browser-local helper for Odoo import preparation: match a supplier CSV to the External IDs in a product export, review exceptions, and download matched rows.

**[Try the free browser beta](https://vendor-id-bridge.zippy-tiger-1052.chatgpt.site/?src=github)**

## Who this is for

Odoo implementers and distributors who already have products in Odoo and need to join a supplier file to product relationship IDs. This is an early, AI-assisted implementation, currently tested with fictional fixtures rather than a live customer database.

## Try it in a minute

1. Open the beta and choose **Try a fictional sample**.
2. Check the three selected columns and the product model.
3. Choose **Compare & review**.
4. Expect **3 matched rows, 1 supplier exception, 0 reference issues**.
5. Export the matched rows or the exceptions report.

The [reference export](examples/products-fictional.csv) and [supplier file](examples/supplier-fictional.csv) are fictional and can also be downloaded separately. The supplier file includes two valid quantity tiers for the same product and one unknown SKU.

## Current behavior

- CSV files only; comma, semicolon, or tab delimiters.
- Exact matching, with optional whitespace trimming. Leading zeros and case are preserved.
- Duplicate reference keys and conflicting External IDs block matched-row export.
- Original supplier values and existing vendor-rule IDs are preserved.
- CSV contents and column names are processed locally and are not uploaded.
- Anonymous per-page usage events and price-interest signals are recorded; no tracking cookie is set.

## Important scope

The tool adds `product_tmpl_id/id` or `product_id/id`. Choose a reference export from the corresponding model and check the field mapping in your own Odoo importer. It does not create products, identify existing vendor price rules, or update a database. Keep the External ID of existing vendor rules for repeat imports. Run Odoo's own **Test** action before any import.

[Official Odoo documentation on imports and External IDs](https://www.odoo.com/documentation/19.0/applications/general/export_import_data.html)

## Feedback wanted

**[Describe your workflow or report a problem](https://github.com/caihua996/vendor-id-bridge-beta/issues/new/choose).**

Useful details: your Odoo version, whether you use templates or variants, the file type you receive, and which manual step remains after trying the beta. Use invented examples only; do not post private supplier or customer files.

We are researching an offline edition with saved column presets at **US$19 once**. It is **not on sale**. A price-interest click is not a purchase, and no paying customers or demand validation are claimed.

Independent project; not affiliated with Odoo.
