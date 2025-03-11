# Changelog

## 0.0.1
First release, the library cames with the following features:
- [x] Captchas
	- [x] Cloudflare Turnstile
	- [x] reCaptcha V3
	- [ ] reCaptcha V2
- [x] Xss prevention
- [x] SQL Injections prevention
- [x] Session Hijacking prevention
- [ ] Brute force attacks prevention


## 0.0.2
1. Fixed file paths for views.
2. Feature: allow to disable auto routes (routes set by the library).
3. Bugfix: disabled checks for the spam filter if the filter is disabled.
4. Feature: added the set_value() function in the form views.
5. Feature: added the anti spam filter.


## 0.0.3
1. Bugfix: added the missing submit button for the register and login forms in case developer decides to disable the captchas.
