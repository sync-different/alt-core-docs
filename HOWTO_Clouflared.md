# HOW-TO Guide: CloudFlared setup

## Summary
There are many ways to make your self-hosted server available remotely via Internet.  For example, using a reverse proxy, port-fordwarding, etc.

This how-to guide will walk you through the steps to create a Cloudflared Tunnel, in order to access your Alt server remotely using a server name resolved by DNS. 
The advantage of tunnel solution is you don't need to do any port forwarding, and you can enable / disable the tunnel at any time.

E.g your Alt server will be accessible using this URL `https://demo.mydns.cc/cass/uiv3/indexv2.htm`

In this example, server name is `demo`, and the domain is `mydns.cc`

## Pre-requisites
- Cloudflare account - If you don't have a Cloudflare account, then sign up and create one at `https://www.cloudflare.com`
  
## Setup steps
### 1 - Set up a domain
- Go to Domain Registration > Manage Domains.
- You will need domain DNS accessible from Cloudflare (e.g. you can register a new domain and host it on Cloudflare, or transfer your existing domain to Cloudflare)

### 2 - Set up a new Tunnel
Once you have created an account, login to CF and Choose `Zero Trust` in the sidebar.

### 3 - Select Networks > Tunnels
Once you are in the ZeroTrust dashboard, select Tunnels.

### 4 - Create Tunnel
Once you are in the Tunnels section, select `+ Create a tunnel`

### 5 - Setup Tunnel
Select Cloudflared option for Tunnel.  Click Next.

### 6 - Name Tunnel
Give your tunnel a name, click Save.

### 7 - Configure Tunnel
Choose your operating system, and follow the instructions to download & install Cloudflared installer.

### 8 - Install Cloudflared
Install Cloudflared connector on your machine.  Once the Connector appears, click next.

### 9 - Route Traffic and Create a Public Hostname
Specify Subdomain, domain, and path for your DNS.  
In the Service section, set the Service Type to `HTTP` and the URL to `localhost:8081`

### 10 - Test the domain
Go to your browser and test with your Public Hostname e.g. `https://myalt.mydomain.cc/cass/uiv3/indexv2.htm`

In this example, the subdomain is `myalt`, the domain is `mydomain.cc`


