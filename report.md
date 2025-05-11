# 📛 Stored XSS in LifterLMS Plugin (v8.0.6)

## Summary
A stored Cross-Site Scripting (XSS) vulnerability was discovered in the **LifterLMS** WordPress plugin (v8.0.6). This allows an authenticated user to inject a JavaScript payload in a course comment, which is then executed in the browser of any user who visits the comment page.

---

## Impact
- Session hijacking (e.g. document.cookie)
- Admin panel access (if viewed by an admin)
- Defacement
- Full control of the WordPress panel in some contexts

---

## Reproduction Steps
1. Install LifterLMS on a local instance.
2. Create a new course.
3. Leave a comment containing the following payload:
   ```html
   <script>alert(document.cookie)</script>

![image](https://github.com/user-attachments/assets/d81602ff-d8aa-4ba0-bef1-fbc3ca23c156)


Notes
The payload was successfully executed and extracted the document.cookie.

I previously reported a vulnerability (report ID #256563) and received $50. I’m thankful and happy to report this more impactful issue.

I attempted to report it via the LifterLMS contact form, but access was blocked, likely due to WAF filtering.

Researcher
Caio Felipe Lima Lopes
📧 caiofelipehlimalopes@gmail.com
