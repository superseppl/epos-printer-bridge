# ePOS Printer Bridge for Odoo – downloads

Print Odoo Online POS receipts to receipt printers in your shop network.

## Printer helper for old printers (Windows)

Only needed for older network receipt printers that don't support Epson ePOS (they only
accept print data on port 9100, e.g. Epson TM-T70). Modern Epson printers work with the
Chrome extension alone.

1. **[Download PrinterHelper.exe](https://github.com/superseppl/epos-printer-bridge/releases/latest/download/PrinterHelper.exe)**
2. Open the downloaded file. If Windows shows "Windows protected your PC", click
   **More info** → **Run anyway**. A message confirms the installation.
3. In Chrome, click the **ePOS Printer Bridge** icon → **Check again**.

The helper installs only for the current Windows user (no administrator rights) into
`%LOCALAPPDATA%\EposPrinterHelper`. It runs only when Chrome sends a print job, connects only
to printers in your local network, and collects no data.

**Remove:** run `PrinterHelper.exe --uninstall` from that folder.
