# Roast Weight Check

A free standalone HTML utility for inspecting weights in Artisan `.alog` files. It shows missing measurements and disagreements between raw and cached weights, then exports a JSON report.

## Use

Save `roast-weight-check.html` to your computer and open it in desktop Chrome. The HTML file contains the application source; no installation or build is needed. Choose your `.alog` files, inspect the report, then select **Download JSON report** to save it. **Show synthetic demo** lets you try the report without a roast file.

Selecting another set of files replaces the report. **Clear** removes the selected files and report from the page. The file picker may show no filename after reading while the completed report remains visible. On narrow screens, scroll the results table horizontally to see Loss and Issues.

## Supported input and report limits

Choose at most 20 files, each up to 1 MiB. Only gram (`g`) weights are supported. Positive weights must be between 0.000001 and 1,000,000,000 g. Zero measurements and absent cached measurements remain unknown. Malformed or unsupported records are rejected with an explanation; compatibility with every Artisan file version is not established.

The report lists raw and cached input/output weights. It flags disagreements without choosing an authoritative value. Identical file contents count once in totals. Files sharing a UUID with different contents are flagged and excluded from totals. A raw/cache conflict excludes the affected measurement from its total and prevents a complete-pair loss calculation. Known input and output totals can cover different sets of records; they are not an inventory balance.

The utility does not change source files or repair their measurements. Review flagged records in your usual roast workflow before relying on them.

## Local processing

The application reads selected files on your device and does not upload them. It has no external dependencies, analytics or network requests. The exported report includes selected filenames and roast UUIDs; review it before sharing.

The checked browser is desktop Chrome 154.0.8037.97. Checks covered file selection, JSON export and a 400 CSS px viewport. Other browsers, touch/trackpad gestures and full keyboard accessibility remain unverified.

## Feedback and license

If you choose to open a repository issue, describe whether the report helped or what failed. Include your browser version. Do not attach roast files or reports containing private information.

The software and embedded synthetic demo use the MIT License. See `LICENSE` and `NOTICES.md`. `SHA256SUMS` lists the package file hashes, excluding the checksum file itself.
