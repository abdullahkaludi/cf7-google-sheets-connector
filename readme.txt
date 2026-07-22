=== GSheetConnector – CF7 Google Sheets Connector with Real-Time Sync ===
Contributors: westerndeal, abdullah17, gsheetconnector
Donate link: https://www.paypal.me/WesternDeal
Tags: contact form 7, google sheets, google sheets integration, google spreadsheet, form submissions
Requires at least: 3.6
Tested up to: 7.0
Requires PHP: 7.4
Requires Plugins: contact-form-7
Stable tag: 5.1.7
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Sync Contact Form 7 submissions to Google Sheets automatically and in real time — no coding, no manual copy-pasting.

== Description ==

**(CF7 Google Sheets Connector)[https://www.gsheetconnector.com/cf7-google-sheet-connector-pro?wp-repo)  connects [Contact Form 7](https://wordpress.org/plugins/contact-form-7/) to [Google Sheets](https://www.google.com/sheets/about/), so every form submission is appended to a spreadsheet the moment it's received. Instead of digging through email notifications, your leads, RSVPs, orders, and inquiries land in one shared, searchable Google Sheet that your whole team can access.

It's a lightweight Contact Form 7 Google Sheets integration built for site owners who want reliable Google Sheets sync without touching a Google Cloud Console — just connect your Google account and map a form to a sheet.

[Homepage](https://www.gsheetconnector.com/) | [Documentation](https://www.gsheetconnector.com/docs/cf7-gsheetconnector/) | [Support](https://www.gsheetconnector.com/support/) | [Live Demo](https://demo.gsheetconnector.com/cf7-google-sheet-connector-pro/)

= Why sync Contact Form 7 with Google Sheets? =

* **Real-time sync** – data is written to your Google Spreadsheet as soon as Contact Form 7 sends the submission, no waiting, no manual export.
* **No spreadsheet skills required** – map a form to a sheet once, and every future submission is added automatically as a new row.
* **A shared, always-up-to-date record** – colleagues can view or filter incoming submissions in Google Sheets without needing WordPress admin access.
* **A safety net for your data** – submissions are also stored locally in your WordPress database, independent of the Google Sheets connection.

= Key features =

**Google Sheets sync**

* Map any Contact Form 7 form to a specific Google Sheet and tab (Sheet Name, Sheet ID, Tab Name, Tab ID).
* Appends a new spreadsheet row on every successful submission (`wpcf7_mail_sent`), including all form field values.
* Supports Contact Form 7's built-in special mail tags — date, time, serial number, remote IP, user agent, page URL, post ID/title, site title, and more.
* Built-in formula-injection protection strips leading `=`, `+`, `-`, and `@` characters from submitted values before they reach your spreadsheet.
* Newly added rows have their formatting cleared automatically so they don't inherit stray cell styling.

**Flexible Google authentication**

* **Quick connect (recommended)** – sign in with your Google account in a couple of clicks. No Google Cloud project or API keys required.
* **Google Service Account** – connect using a service-account JSON key for server-to-server, no-human-login setups (great for agencies and automated environments).

**CF7 Database – local submission backup**

* Every submission is optionally stored in your own WordPress database, independent of the Google Sheets connection, so nothing is lost if a sync fails.
* Browse, search, and paginate submissions per form, mark entries as read/unread, and resend entries to your spreadsheet using the bulk "Send to Spreadsheet" action.

**Diagnostics you can actually use**

* A dedicated error log records Google authentication and API failures, with automatic de-duplication so one recurring issue doesn't flood the log.
* A System Status page reports your server/plugin environment and tails your WordPress debug log for quick troubleshooting.

**Built for growing setups**

* A WordPress Dashboard widget lists every connected form and its linked Google Sheet at a glance.
* An Extensions tab lets you discover and one-click install companion connectors for WPForms, Gravity Forms, Ninja Forms, Forminator, Formidable Forms, Fluent Forms, Elementor, Avada, Divi, WooCommerce, Easy Digital Downloads, and WordPress comments.

= Unlock more with GSheetConnector PRO =

The free version covers everything you need for a solid, one-sheet-per-form Google Sheets integration. [GSheetConnector PRO](https://www.gsheetconnector.com/cf7-new-2026#compare) adds:

* Multiple Google Sheet feeds per form (send one form's data to several spreadsheets).
* Custom column ordering, header renaming, and per-field enable/disable.
* Automatic sheet/tab detection instead of manual ID entry.
* Header and row styling — freeze header row, background colors, and more.
* Conditional logic to control when a submission is synced.
* File attachment and Google Drive storage support.
* CSV export of your locally stored submissions.
* Role-based permissions and priority support.

See the full [feature comparison](https://www.gsheetconnector.com/cf7-new-2026#compare) for details.

= Compatibility =

* Works with the latest versions of WordPress and Contact Form 7.
* Compatible with Contact Form 7 forms embedded via page builders such as Elementor, Divi, and Avada.
* Supports WordPress multisite (each site authenticates its own Google connection).

== Installation ==

= 1. Install and activate =

1. In your WordPress admin, go to **Plugins → Add New**, search for "CF7 Google Sheets Connector", and click **Install Now**, then **Activate**. Alternatively, upload the `cf7-google-sheets-connector` folder to `/wp-content/plugins/` and activate it from the **Plugins** screen.
2. Make sure [Contact Form 7](https://wordpress.org/plugins/contact-form-7/) is installed and active — this plugin requires it.

= 2. Connect your Google account =

1. Go to **Contact → Google Sheets → Integration**.
2. Click **Sign in with Google** and approve the requested Google Sheets and Google Drive permissions in the popup. (Prefer not to use your personal Google login? Choose the **Service Account** method instead and paste in a service-account JSON key from Google Cloud Console.)
3. Once connected, the Integration tab will show your authenticated Google account.

= 3. Prepare your Google Sheet =

1. Create (or open) a spreadsheet at [sheets.google.com](https://sheets.google.com/).
2. Note the Sheet Name, Sheet ID, Tab Name, and Tab ID (visible in the sheet's URL and tab settings).
3. In row 1 of the tab, add your column headers. The first column should be `date`. For every other column, use the exact Contact Form 7 field/mail-tag name (e.g. `your-name`, `your-email`, `your-subject`, `your-message`).
4. Column headers must be lowercase, with hyphens instead of spaces, and no leading numbers, underscores, or quotes.

= 4. Connect your form =

1. Edit the Contact Form 7 form you want to sync, then open its new **Google Sheets** tab.
2. Enter the Sheet Name, Sheet ID, Tab Name, and Tab ID you noted earlier, then click **Save**.
3. Submit a test entry on your form and confirm it appears as a new row in your Google Sheet.

That's it — every future submission to that form will now sync to your spreadsheet automatically.

== Frequently Asked Questions ==

= Data isn't showing up in my Google Sheet — what should I check? =

Work through these in order:

1. Confirm the form's **Google Sheets** tab has a saved Sheet Name, Sheet ID, Tab Name, and Tab ID.
2. Confirm your Google connection is still valid on the **Integration** tab. If it shows as expired or invalid, reconnect.
3. Confirm your sheet's row 1 headers exactly match your form's field/mail-tag names — lowercase, hyphenated, no leading numbers, underscores, or spaces. A mismatched header simply stays blank; it won't throw a visible error.
4. If you're using a Service Account, make sure the spreadsheet is explicitly shared (as Editor) with the service account's email address.
5. Check the **Error Log** on the System Status tab for authentication or permission errors.

= The form submits, but the button just keeps spinning — is that this plugin? =

The submit/spinner behavior is controlled by Contact Form 7 itself, not this plugin. This plugin only runs after Contact Form 7 has already confirmed the message was sent, so a stuck spinner usually points to a Contact Form 7 or email-delivery issue rather than the Google Sheets connection.

= How do I connect my Google account? =

On **Contact → Google Sheets → Integration**, click **Sign in with Google**, approve the requested permissions in the popup, and you're connected — no Google Cloud Console setup required. If you'd rather not sign in with a personal account, use the **Service Account** method instead.

= Can I use a Google Service Account instead of signing in with my Google account? =

Yes. Create a service account and JSON key in Google Cloud Console, share your target spreadsheet with the service account's email address (shown in the plugin once your key validates), then paste the JSON key into the Service Account field on the Integration tab.

= Can I connect more than one Contact Form 7 form to Google Sheets? =

Yes, every form can be connected to its own Google Sheet independently. The free version supports one sheet/tab feed per form; [GSheetConnector PRO](https://www.gsheetconnector.com/cf7-new-2026#compare) adds multiple feeds per form.

= What happens if the Google Sheets sync fails for a submission? =

If the local **CF7 Database** feature is enabled (Settings → General Settings), every submission is stored in your WordPress database regardless of whether the Google Sheets sync succeeds. You can review those entries and resend them to your spreadsheet using the "Send to Spreadsheet" bulk action.

= Where is my form data sent, and is it secure? =

Submitted data is sent directly from your WordPress site to Google's official Sheets and Drive APIs over an authenticated OAuth 2.0 (or service-account) connection — the plugin does not route your form data through third-party servers. Values are sanitized before being written to your sheet, and a formula-injection guard strips characters that could otherwise execute as spreadsheet formulas.

= Does uninstalling the plugin delete my data? =

By default, uninstalling keeps your saved settings so you can reinstall without reconnecting. If you'd like your stored Google connection details removed on uninstall, enable the "Delete data on uninstall" option under Settings → General Settings before removing the plugin.

= Will this work with my page builder (Elementor, Divi, Avada, etc.)? =

Yes. As long as you're using an actual Contact Form 7 form — whether placed directly or embedded via a page builder — the Google Sheets tab and sync will work the same way.

== Screenshots ==

1. Connecting to Google — authentication and permissions screen.
2. The Google Sheets tab inside the Contact Form 7 editor, where you enter the Sheet Name, Tab Name, and field headers.
3. Role Permissions settings screen.
4. CF7 Database — browsing locally stored form submissions.
5. Version Control (Beta Program) settings.
6. System Status — environment info and debug log viewer.

== Changelog ==

= 5.1.7 (22-05-2026) =
* Added: Custom database tables for storing plugin data instead of post meta to improve performance and data management.
* Added: Delete alert message and confirmation popup in Feed Settings.
* Added: Dashboard tab for quick access to plugin information, notices, and settings.
* Fixed: Proper handling and display of error messages when required Google Sheets and Google Drive permissions are not granted in the Integration tab.
* Fixed: Improved handling of invalid OAuth tokens to prevent repeated debug log entries on page refresh.
* Fixed: Security-related issues.
* Fixed: Activate, Install, and Deactivate functionality issues in the Extensions tab.

= 5.1.6 (10-02-2026) =
* Fixed: Fixed Freemius integration issue.

= 5.1.5 (04-02-2026) =
* Fixed: Admin notices not getting closed and showing error.

= 5.1.4 (26-12-2025) =
* Fixed: OAuth authentication failure caused by API request timeout and PHP 8.2 compatibility issues when saving API credentials.
* Fixed: Permission issues with the plugin settings page by switching to the "manage_options" capability.
* Improved: Code compatibility based on WordPress guidelines.

= 5.1.3 (28-11-2025) =
* Updated: Made few performance tweaks to minimize unnecessary API calls and lower the overall quota usage.

= 5.1.2 (14-11-2025) =
* Fixed: Updated the text domain name.
* Fixed: Improved responsive CSS.
* Updated: Updated the header logo and the dashboard widget logo.

= 5.1.1 (13-10-2025) =
* Updated: The plugin name from "Google Sheet Connector for CF7" to "GSheetConnector for CF7".

= 5.1.0 (27-09-2025) =
* Updated: The plugin name from "CF7 Google Sheet Connector" to "Google Sheet Connector for CF7".

= 5.0.22 (18-09-2025) =
* Updated: Readme file updated.
* Fixed: UI improvements.
* Fixed: Debug log display moved to the uploads folder directory.

= 5.0.21 (26-06-2025) =
* Fixed: Compatible with Contact Form 7 version 6.1 (latest version).

= 5.0.20 (22-04-2025) =
* Added: Moved saving of credentials to database for Auto API Integration.

= 5.0.19 (27-01-2025) =
* Fixed: Minor UI changes.

= 5.0.18 (23-01-2025) =
* Fixed: Vulnerabilities issues.

= 5.0.17 (18-12-2024) =
* Added: Freemius integration.
* Added: Showcased the "Manual Method" button on the Integration tab.
* Added: "Requires By" in our plugin and "Required By" in the parent plugin.

= 5.0.16 (29-11-2024) =
* Fixed: Alert displayed while moving to another page after saving settings.
* Fixed: Undefined error while clicking on "Copy to Clipboard" button.

= 5.0.15 (09-08-2024) =
* Fixed: Fix the CSS conflict with the Contact Form 7 plugin.

= 5.0.14 (07-08-2024) =
* Added: Display a notification when authentication expires.

= 5.0.13 (30-07-2024) =
* Fixed: Google hasn't verified this app error.

= 5.0.12 (26-06-2024) =
* Security: Enhanced user input sanitization to prevent malicious code execution in connected Google Sheets.

= 5.0.11 (11-06-2024) =
* Fixed: Not allowing users to enter the administration screen.

= 5.0.10 (07-06-2024) =
* Fixed: Vulnerabilities issues.

= 5.0.9 (09-04-2024) =
* Added: UI changes.

= 5.0.8 (11-03-2024) =
* Added: Links for support and docs.
* Added: Showcasing PRO features in the Google Sheets tab.

= 5.0.7 (11-12-2023) =
* Updated: UI changes for the tag list in the Google Sheet tab under Contact Form settings.
* Fixed: Resolved active-plugins listing issue in the System Status tab.

= 5.0.6 (05-10-2023) =
* Fixed: Resolved debugging view, open and close link systematically.
* Added: Error message for users without Google Drive and Google Sheets permissions.

= 5.0.5 (03-10-2023) =
* Added: Get Code button replaced with the Sign in with Google button.
* Added: Alert for users without Google Drive and Google Sheets permissions during authentication.
* Added: Redesigned System Status and Error Log for improved functionality and user experience.
* Fixed: Vulnerabilities issues.

= 5.0.4 (24-06-2023) =
* Added: A few more minor UI changes.

= 5.0.3 (04-05-2023) =
* Added: Minor UI changes.

= 5.0.2 (27-04-2023) =
* Fixed: Vulnerabilities issues.

= 5.0.1 (23-02-2023) =
* Added: Remove access permission from Google account while deactivating authentication.
* Fixed: Made compatible with the "Smart Grid-Layout Design for Contact Form 7" plugin.

= 5.0.0 (05-08-2022) =
* Updated: API library to latest version 2.12.6 and Guzzle library to version 7.4.3.
* Migrated: OAuth OOB to an alternative method, as it was deprecated from 3rd October 2022.

= 4.9.2 (19-01-2022) =
* Fixed: 'Line Break' on textarea issue resolved.

= 4.9.1 =
* Fixed: Undefined index issue.

= 4.9 =
* Fixed: Issue with incorrect or expired auth code.
* Fixed: Deactivation issue while adding incorrect and expired auth code.
* Fixed: Displaying of error while setting Contact Form initially.

= 4.8 =
* Fixed: Vulnerability issues.
* Added: 'Upgrade to PRO' links.
* Added: Google Sheet link in settings.
* Updated: Google API version to 2.10.1 and Guzzle library to 7.3.0.
* Various: UI changes.

= 4.7 =
* Added: Display authenticated email ID on the Integration page.
* Fixed: Data not getting saved under exact column names.
* Fixed: Composer functions to avoid clashing with other plugins.

= 4.6 =
* Updated: API library to avoid conflicts with "Facebook for WordPress" and other plugins.

= 4.5 =
* Fixed: Saving of incorrect file name to the Google Sheet.

= 4.4 =
* Fixed: Special mail tag issue caused by Contact Form 7 5.2.2.

= 4.3 =
* Fixed: Special mail tag issue caused by Contact Form 7 5.2.1.

= 4.2 =
* Added: Ability for users to deactivate authentication.
* Fixed: Conflicts error.

= 4.1 =
* Fixed: Displaying of single quote sign in front of numeric and date values.

= 4.0 =
* Upgraded: Google APIs Client Library to version v4.
* Added: Support for capital letters, underscores, numbers, and spaces in CF7 input field names and header names.
* Fixed: Addition of backslash in front of apostrophes and quotation marks.

= 3.0 =
* Updated: API library.
* Added: Ability to permanently close the Google Sheet Connector Pro notice.

= 2.9 =
* Added: Hide Google Sheet menu and settings based on user role Contact Form 7 edit capabilities.

= 2.8 =
* Fixed: Displaying of Google Sheet Connector notice to be dismissible.

= 2.7 =
* Various: UI changes.
* Fixed: No longer deletes authentication data when upgrading to the Pro version.
* Changed: Renamed classes and functions to avoid conflicts when upgrading to the Pro version.

= 2.6 =
* Various: UI changes at the Google Sheet tab under Contact Form settings.

= 2.5 =
* Removed: A prior connection limitation.

= 2.4 =
* Fixed: Connections of Contact Forms with Google Sheet.
* Added: Limitation to connect the first 5 Contact Forms to Google Sheet.

= 2.3.1 =
* Fixed: Images not being displayed.

= 2.3 =
* Fixed: Integration issues.
* Fixed: Functionality issues of limitations from the previous update.

= 2.2 =
* Various: UI changes and bug fixes.
* Added: Limitation for the number of Contact Forms that can connect to Google Sheet.

= 2.1 =
* Added: Google Sheet Connector dashboard widget for quick access to connected forms.
* Added: Option to clear logs.
* Fixed: Multisite plugin activation issue.

= 2.0 (11-06-2018) =
* Fixed: Bypassing of Contact Form 7's built-in data validation.

= 1.9 =
* Fixed: Contact form data not being fetched to Google Sheet.

= 1.8 =
* Fixed: Page hijacking (loading issue) on the front end after submit actions.
* Added: Integrated new special mail tags (including Flamingo serial number) with the spreadsheet without underscores.

= 1.7 (26-08-2017) =
* Added: Integrated special mail tags with the spreadsheet without underscores.
* Fixed: Date format to match WordPress standards.

= 1.6 =
* Updated: Google Spreadsheet library.
* Changed: Class names for the PHP Google Auth library.
* Added: Delete all data on uninstallation of the plugin.

= 1.5 =
* Fixed: Class name conflicts with other plugins.
* Fixed: Issue sending hidden fields via a dynamic-text extension.
* Added: Settings link on plugin activation.

= 1.4 =
* Fixed: 500 Internal Server Error when sheet name or tab name is not set.

= 1.3 =
* Added: .pot file for easier translation.

= 1.2 =
* Updated: Plugin description and related details.

= 1.1 =
* Fixed: Date format and display issues related to non-English dates.
* Fixed: Class name conflict with other plugins.

= 1.0 =
* First public release. Integrated Contact Form 7 with Google Sheets.

== Upgrade Notice ==

= 5.1.7 =
This update introduces new database tables for plugin data, a Dashboard tab, and several stability and security fixes. Back up your site before updating, as recommended for any plugin update.
