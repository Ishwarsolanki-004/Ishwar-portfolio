# DNS Walkthrough

## My current website

My portfolio is currently hosted on GitHub Pages:

https://ishwarsolanki-004.github.io/Ishwar-portfolio/

The site is served over HTTPS, so visitors can open it securely in a browser.

## What is DNS?

DNS (Domain Name System) translates a human-readable domain name into the destination needed to reach a website. Instead of remembering an IP address, a user can type a domain such as `yourname.example.com`.

When someone enters a domain name, the browser needs to find the DNS information for that name. A DNS resolver looks for the answer, following the DNS hierarchy and contacting the relevant nameserver when the answer isn't already cached.

The nameserver stores DNS records for the domain. These records tell the resolver where different services or subdomains should point.

## What is a CNAME record?

A CNAME (Canonical Name) record makes one domain name an alias of another hostname.

For example, if I later receive the FlyRank subdomain `ishwar.flyrank.ai`, the CNAME record could point that hostname to the hostname GitHub Pages provides for my site.

The important point is that a CNAME points to another hostname, not directly to an IP address.

## What happens when someone visits my future subdomain?

1. The visitor enters `ishwar.flyrank.ai` in their browser.
2. The browser needs to find where that hostname is hosted, so DNS resolution begins.
3. The DNS resolver checks its cache. If it doesn't already have the answer, it queries the appropriate nameserver.
4. The nameserver returns the CNAME record configured for the subdomain.
5. DNS resolution follows that hostname to find the hosting destination.
6. The browser connects to GitHub Pages over HTTPS.
7. GitHub Pages returns my portfolio files, and the website is displayed.

DNS changes can take some time to propagate, since resolvers cache DNS records according to their TTL (time to live).

## What I'll do when my FlyRank subdomain is provisioned

When the FlyRank subdomain is provided, I'll add the custom domain in GitHub Pages' settings, configure the required CNAME record with my DNS provider, wait for DNS propagation, and verify that the site loads over HTTPS with the browser padlock showing.

My current GitHub Pages site doesn't need to be rebuilt for this. The custom domain acts as a pointer to the existing hosted site.
