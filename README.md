## what
[mercury](https://github.com/Alex313031/Mercury) workflow optimized for performance/ocd (ungodly amount of tabs/tab groups) + container division between clearnet and tor proxy

![my peak open tabs count](/pics/tabs.png)

## how
- "profile" folder is quite literally that. drag it into your firefox/mercury profile directory. enter the url "about:profiles" for your dir.
- sidebery config in case you only want that, import via sidebery: ``` settings/help/"import addon data" ```

## tor (stupid)
> [!CAUTION]
you really shouldnt be using the tor network through anything other than the tor browser, so if security/privacy is your TOP priority, then please just use that. [follow basic practices](https://pastebin.com/Ppj7yh4i). but if you want your traffic masked from, say, your ip, this is what i did.

- note: doing this on linux or another operating system will follow the same essential process: download and run the tor package, allowing you to access the network through proxy. you can find some specific guide for your OS elsewhere.

#### macos guide (>=14.0 sonoma)
install tor package and run (pre-req: [homebrew](https://brew.sh/))
```
brew install tor
brew services start tor
```
proxy autoconfig
```
sudo curl https://start9.com/assets/proxy.pac --output /Library/WebServer/Documents/proxy.pac
```
enable apache service
```
sudo launchctl enable system/org.apache.httpd
sudo launchctl kickstart system/org.apache.httpd
```
now, open system settings. go to: ``` network/(your adapter, typically wifi)/details/proxies ```

enable "automatic proxy configuration" and input this url: ``` http://localhost/proxy.pac ```

### using tor through sidebery container
here is my config:

![container proxy](/pics/sidebery-container-proxy.png)

any of the asthetic settings you can change, of course

## thoughts
i believe i still need to configure my user.js. if you'd like to know more, see [arkenfox](https://github.com/arkenfox/user.js)
