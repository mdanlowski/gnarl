# GNARL
### Ruby on Rails URL shortener/forwarder

https://git.heroku.com/gnurl.git

### Features:
- Any valid link is digested into a form of `hostname + 8 character hash`
- The hash is generated using SHA2 on user provided url: first 4 and last 4 chars
- If /although chances are low/ the above combination already exists, a new is generated adding a suffix consiting of SecureRandom hexchain, hence the name: **Gnarl**, because it's kind of glued up to the main part
- The server opens the page in the background and checks if the address returns anything, if not, or if it's a 400 - it will not be accepted
- Existing URLs are not repeatedly saved
- URL is stripped off preceding and trailing whitespace and validated with a URL regex (serverside)
