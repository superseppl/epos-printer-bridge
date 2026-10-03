# ePOS Printer Bridge for Odoo – downloads

Print Odoo Online POS receipts to the receipt printer in your shop network. Browsers block
this on their own (the Odoo page is HTTPS, the printer is a local HTTP device), so there are
two ways to make it work. Pick one:

| | **Option 1: Chrome extension** | **Option 2: Odoo Kasse desktop app** |
|---|---|---|
| What | Extension for Chrome/Edge, Odoo stays in the normal browser | Own Windows program that opens the Odoo POS in its own window |
| Modern Epson printers (ePOS) | ✅ extension only | ✅ |
| Old printers (port 9100, e.g. Epson TM-T70) | ✅ plus the free printer helper (Windows) | ✅ built in |
| Install | from the Chrome Web Store link (test: load unpacked) | none, just start the .exe |
| Systems | Windows (old printers), any Chrome system (ePOS printers) | Windows 10/11 |
| Status | in Chrome Web Store review | test version, currently set up for braeu.odoo.com and printer 192.168.1.200 |

## Option 1: Chrome extension (+ printer helper for old printers)

1. Install the extension:
   - **Chrome Web Store:** use the link you received.
   - **Test version:** download `epos-printer-bridge-extension-1.1.0-TEST.zip` from the
     [test release](https://github.com/superseppl/epos-printer-bridge/releases/tag/test-2026-10-03),
     unzip it, open `chrome://extensions`, switch on **Developer mode** (top right),
     click **Load unpacked** and choose the unzipped folder.
2. Click the **ePOS Printer Bridge** icon in Chrome and add your printer's IP address
   (or click **Allow** when it asks after the first print).
3. **Old printer only:** in the extension window click **Download printer helper**
   ([direct link](https://github.com/superseppl/epos-printer-bridge/releases/latest/download/PrinterHelper.exe)),
   open the file (if Windows warns: **More info** → **Run anyway**), then click **Check again**.
4. Open the Odoo POS in Chrome and print.

The printer helper installs only for the current Windows user (no administrator rights) into
`%LOCALAPPDATA%\EposPrinterHelper`, runs only when Chrome sends a print job and connects only to
printers in your local network. Remove it with `PrinterHelper.exe --uninstall`.

## Option 2: Odoo Kasse desktop app

1. Download `OdooKasse-Braeu.exe` from the
   [test release](https://github.com/superseppl/epos-printer-bridge/releases/tag/test-2026-10-03)
   into its own folder, e.g. `C:\OdooKasse`.
2. Start it (if Windows warns: **More info** → **Run anyway**) and log in to Odoo once;
   the login is kept in the `browser-data` folder next to the program.
3. Open the register and print. It tries the modern Epson way first and falls back to port 9100
   for old printers automatically.

Problems with printing are written to `printer.log` next to the program. Needs the Microsoft
Edge WebView2 Runtime (preinstalled on current Windows 10/11).

## Privacy

Neither option collects or sends any data; print jobs go only from your computer to your own
printer. [Privacy policy / Datenschutzerklärung](PRIVACY.md)
