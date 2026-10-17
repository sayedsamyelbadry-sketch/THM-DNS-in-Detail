# 🌐 TryHackMe – DNS in Detail

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)
![Category](https://img.shields.io/badge/Category-Networking-blue)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

# 📝 Overview

**DNS in Detail** introduces the fundamentals of the **Domain Name System (DNS)**, explaining how domain names are translated into IP addresses and how DNS resolution works behind the scenes.

The room also covers different DNS record types, the DNS hierarchy, recursive and authoritative DNS servers, and practical DNS enumeration using common Linux tools.

---

# 🎯 Learning Objectives

- Understand how DNS works.
- Learn the DNS resolution process.
- Differentiate between Recursive and Authoritative DNS servers.
- Identify common DNS record types.
- Perform DNS enumeration using Linux tools.
- Understand the role of DNS during Reconnaissance.

---

# 📚 Key Concepts

## 🌍 What is DNS?

DNS (**Domain Name System**) translates human-readable domain names into IP addresses.

Example:

```
google.com
        ↓
142.250.xxx.xxx
```

Without DNS, users would have to remember IP addresses instead of website names.

---

## 🌐 DNS Resolution Process

When requesting a website, DNS follows this sequence:

```
Client
   ↓
Recursive DNS Server
   ↓
Root Server
   ↓
Top-Level Domain (TLD) Server
   ↓
Authoritative DNS Server
   ↓
IP Address
```

The browser then connects to the returned IP address.

---

## 🗂 DNS Hierarchy

```
.
│
├── .com
│      │
│   google
│      │
│     www
```

The DNS hierarchy consists of:

- Root Server
- Top-Level Domain (TLD)
- Domain Name
- Subdomain

---

# 📌 DNS Record Types

### A Record

Maps a domain to an IPv4 address.

Example:

```
google.com → 142.250.x.x
```

---

### AAAA Record

Maps a domain to an IPv6 address.

---

### CNAME Record

Creates an alias that points one domain to another domain.

Example:

```
shop.example.com
        ↓
shops.myshopify.com
```

---

### MX Record

Specifies the mail server responsible for receiving emails.

The lowest priority number has the highest priority.

---

### TXT Record

Stores text-based information.

Common uses:

- SPF
- DKIM
- DMARC
- Domain Verification

---

# ⚡ Recursive vs Authoritative DNS

### Recursive DNS Server

- Receives client requests.
- Queries other DNS servers.
- Caches results.
- Usually provided by the ISP.

---

### Authoritative DNS Server

- Stores the original DNS records.
- Returns the final answer for the requested domain.

---

# ⏱ Time To Live (TTL)

TTL determines how long a DNS record remains cached.

- Lower TTL → Faster updates.
- Higher TTL → Better performance and fewer DNS queries.

---

# 🛠 Practical Commands

### nslookup

```bash
nslookup google.com
```

---

### dig

```bash
dig google.com
```

Specific records:

```bash
dig google.com A

dig google.com AAAA

dig google.com MX

dig google.com TXT
```

---

# 🔍 Why DNS Matters in Pentesting

DNS enumeration is one of the first steps during the **Reconnaissance** phase.

It helps identify:

- Subdomains
- Mail Servers
- Third-party Services
- Cloud Providers
- Verification Records
- Infrastructure Information

---

# 💡 Skills Gained

- DNS Fundamentals
- DNS Resolution
- DNS Enumeration
- Networking Basics
- Linux Networking Tools
- Reconnaissance Techniques

---

# 🏁 Conclusion

This room provided a strong understanding of how DNS operates and why it is essential in Web Application Security and Penetration Testing.

Mastering DNS allows security professionals to gather valuable information about a target before attempting further enumeration or exploitation.

---

## ⭐ Key Takeaways

- DNS translates domain names into IP addresses.
- Recursive DNS servers perform lookups and cache responses.
- Authoritative DNS servers store the official DNS records.
- A, AAAA, CNAME, MX, and TXT are the most common DNS records.
- TTL controls how long DNS records stay cached.
- DNS Enumeration is an essential Reconnaissance technique in Web Penetration Testing.

---

> 🚀 This room is part of my **Web Penetration Testing & Red Team** learning roadmap on TryHackMe.
