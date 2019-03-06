# GNARL
### Ruby on Rails URL shortener/forwarder

http://gnurl.herokuapp.com/

### Features:
- Any valid link is digested into a form of `hostname + 8 character hash`
- The hash is generated using SHA2 on user provided url: first 4 and last 4 chars
- If /although chances are low/ the above combination already exists, a new is generated adding a suffix consiting of SecureRandom hexchain, hence the name: **Gnarl**, because it's kind of glued up to the main part
- The App tries to open the page in the background and checks if the address returns anything, if not, or if it's a 400 - the link will not be accepted **This works only locally due to Heroku internal limitations**

### TURNING ON/OFF THE FEATURE LOCALLY:
#### Uncomment/Comment these lines
``` ruby
15|      # see if the link makes sense
16|        content = self.inspect_link(input)
17|        if content.class == Hash
18|          return content
19|        end
```
- Existing URLs are not repeatedly saved
- URL is stripped off preceding and trailing whitespace and validated with a URL regex (serverside)
