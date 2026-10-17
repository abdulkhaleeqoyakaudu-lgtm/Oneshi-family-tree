# ONESHI FAMILY — ready-to-open Windows package

## Start the website on Windows
1. Extract this ZIP into a normal folder (do not run it from inside the ZIP preview).
2. Install Node.js 20 or newer from https://nodejs.org/ if it is not already installed.
3. Double-click `start-windows.bat`. Allow a few minutes on the first launch while dependencies install.
4. Your browser opens the administrator login at http://localhost:3000/admin.
5. Keep the black server window open while using the site.

## Administrator login
- Email: `abdulkhaalliiqq@gmail.com`
- Password: the password configured in `.env` (the requested value is currently set there).

## Included
- Professional responsive ONESHI FAMILY landing page and member portal.
- Family tree data transcribed from the names and branch links in the supplied `02 innovation.zip`. Please review the tree because some original pages had inconsistent labels or incomplete child lists.
- Admin dashboard for reviewing applications, approving/rejecting/suspending members, generating manual six-digit activation codes after payment approval, and publishing announcements.
- Phone-number-only member registration/login (email is not required for members).
- ₦2,000 one-time lifetime membership fee instructions for transfers from any Nigerian bank to the supplied OPay account.

## Important setup limits
- This package runs locally on the computer where it is extracted; it is not published on the internet.
- Payments are direct bank transfers. The administrator must confirm the money arrived in OPay before clicking Approve. A screenshot or reference alone is not confirmation.
- Manual verification is included at no SMS cost: after you confirm the money arrived in OPay, click “Approve payment & generate code” in the admin dashboard. Give the six-digit code shown beside that application to the member yourself by phone or WhatsApp. The member logs in and enters the code to activate their account. The website does not send SMS or WhatsApp automatically.
- Before publishing online, change the short administrator password in `.env`, use HTTPS, and configure production session security. Never share `.env` publicly.
- Back up the `data` folder; it contains the local SQLite database and family-tree data.

## Personal member login codes

Members apply using their phone number and payment reference; they do not create a password. After you verify the ₦2,000 transfer in your OPay account, sign in to `/admin` and click **Approve payment & generate code**. A unique personal login code is shown once in a pop-up. Copy it and give it privately to that member. The code is stored as a bcrypt hash and is linked to that member's registered phone number. Members log in with their phone number and personal code; the browser session keeps them signed in on that device for up to 8 hours, subject to browser/session settings. If a code is lost, use the database/admin process to reset it; this version does not provide a self-service reset button.

Important: the code is a reusable bearer secret, so a member who shares it may allow someone else to use it with their phone number. Tell members not to share it. For stronger identity assurance, add phone OTP or another second factor later.
