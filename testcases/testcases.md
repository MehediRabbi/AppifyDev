2\) Test Cases / Checklist (30 test cases)



Severity: Critical (C), High (H), Medium (M), Low (L).



I'll present them as compact items you can paste into a spreadsheet (columns: ID, Title, Steps, Expected Result, Severity).



TC-01 — App Launch



Steps: Install app → Launch.



Expected: App launches within 5s, splash (if any) proceeds to home/login. No crash.



Severity: H



TC-02 — Install/Update



Steps: Install from Play Store; upgrade from previous version (if available).



Expected: Install/upgrade completes without data loss or crash.



Severity: M



TC-03 — First-time onboarding flow



Steps: Launch app first time → complete onboarding screens.



Expected: Onboarding completes, user lands on main screen.



Severity: M



TC-04 — Login with valid credentials



Steps: Navigate to login → enter valid email/phone + password → submit.



Expected: Login successful; user lands on dashboard. Token/session stored securely.



Severity: C



TC-05 — Login with invalid credentials



Steps: Use wrong password → submit.



Expected: Error message shown (no sensitive info), remains on login page.



Severity: H



TC-06 — Password reset flow



Steps: Click “Forgot password” → request reset with registered email → follow reset.



Expected: Password reset email sent (web: confirm HTTP 200). Reset completes.



Severity: H



TC-07 — Sign up / Registration



Steps: Fill registration form with valid inputs → submit.



Expected: Account created; user logged in or confirmation shown.



Severity: H



TC-08 — Input validation — email format



Steps: Enter invalid email in signup/login.



Expected: Client-side validation prevents submit and shows message.



Severity: M



TC-09 — Offline behavior



Steps: Disable network → perform key actions (send message, load page).



Expected: App gracefully shows offline state, queues messages or errors appropriately; no crash.



Severity: H



TC-10 — Send / Receive Chat Message (core)



Steps: Open chat → send text message → another test account/echo response expected.



Expected: Message appears in timeline with timestamp; delivery status updates if supported.



Severity: C



TC-11 — Send long message / large payload



Steps: Paste a 10k+ character message → send.



Expected: Either successfully sent or prevented with clear validation; app not crashed.



Severity: M



TC-12 — Attach \& send image



Steps: Attach an image from gallery → send.



Expected: Thumbnail shown and message sent; image loads for recipient.



Severity: H



TC-13 — Attach unsupported file type



Steps: Try to attach .exe or other unsupported type.



Expected: App shows “unsupported file type” message; doesn’t crash.



Severity: M



TC-14 — Play media inside message



Steps: Tap image/video in chat to view/play.



Expected: Viewer opens and plays without crash.



Severity: M



TC-15 — UI responsiveness — rotation



Steps: Rotate device in several screens (login, chat, settings).



Expected: Layout adapts and no layout overlap; state preserved.



Severity: M



TC-16 — Background / foreground



Steps: Send app to background → perform heavy operations → bring back to foreground.



Expected: Session preserved; no inconsistent UX or data loss.



Severity: H



TC-17 — Session expiry / logout



Steps: Logout explicitly; also simulate session expiry by clearing token.



Expected: User required to re-login; tokens not reused.



Severity: H



TC-18 — Security: HTTP vs HTTPS



Steps: Visit site pages; check for mixed content and HTTPS.



Expected: All endpoints are HTTPS; no mixed content warnings.



Severity: H



TC-19 — Security: input XSS in chat



Steps: Send <script>alert(1)</script> as message or input.



Expected: Input sanitized; no JS execution on web clients.



Severity: C



TC-20 — Accessibility: TalkBack / screen reader



Steps: Enable TalkBack → navigate login and core screens.



Expected: All interactive elements have labels/readouts in logical order.



Severity: H



TC-21 — Accessibility: font scaling



Steps: Increase system font to 200% → open key screens.



Expected: Layout remains usable; no truncated buttons preventing use.



Severity: M



TC-22 — Web: Console errors



Steps: Open echogpt.live and apptestingservice.com in Chrome → check dev console.



Expected: No uncaught exceptions or 500 network responses.



Severity: H



TC-23 — Web: Responsive breakpoints



Steps: Resize browser to mobile widths (375px, 768px).



Expected: Layout adapts; nav and CTA visible and usable.



Severity: M



TC-24 — Rate limiting / retry behavior



Steps: Rapidly send multiple requests (e.g., many messages); observe app behavior.



Expected: App handles throttling gracefully; no crash.



Severity: M



TC-25 — Localization / language support



Steps: If other languages supported, switch locale or set device language.



Expected: UI translates correctly; no layout break.



Severity: L



TC-26 — Deep link / notification open



Steps: Click a notification or deep link (if available).



Expected: App opens to correct screen and correct back navigation.



Severity: H



TC-27 — Data storage \& privacy



Steps: Check app storage, clear app data, then re-login.



Expected: Personal data cleared after uninstall or clear; no leakage between accounts.



Severity: H



TC-28 — Search functionality



Steps: Use search (if present) with common/edge queries, special chars.



Expected: Relevant results; no failure on special chars.



Severity: M



TC-29 — Clipboard \& copy/paste



Steps: Copy message contents → paste into another field.



Expected: Clipboard works; sensitive fields (passwords) masked on paste.



Severity: L



TC-30 — Logout while offline



Steps: Disable network → attempt logout.



Expected: App either logs out locally or shows appropriate error; state consistent.



Severity: M

