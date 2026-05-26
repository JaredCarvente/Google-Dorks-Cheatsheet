# Google Dorks Cheatsheet

## Introduction

**Google Dorks** (also known as Google Hacking) are advanced search queries that use special operators to filter and narrow down search results beyond a typical Google search. They are widely used in **OSINT (Open Source Intelligence)** investigations, security research, and penetration testing to find specific information about people, companies, or systems that is publicly indexed by search engines.

This cheatsheet focuses on social media dorks and API endpoints useful for gathering publicly available information. Replace `username` or `USER_ID` with the actual target value before using each query.

> ⚠️ **Disclaimer:** Use these techniques responsibly and only on accounts/systems you have permission to investigate. Misuse may violate terms of service or local laws.

---

## Facebook

Search for public posts made by a specific user on Facebook.

```
"username" site:facebook.com inurl:posts
```

---

## Instagram

Find a user's public profile on Instagram.

```
site:instagram.com "username"
```

Search for a username using the `@` mention format.

```
site:instagram.com "@username"
```

Find public posts by a specific user (format 1).

```
"username" "instagram.com/p/" site:instagram.com
```

Find public posts by a specific user (format 2).

```
"username" site:instagram.com inurl:"/p/"
```

Find public posts by a specific user (format 3).

```
"username" site:instagram.com inurl:/p/
```

---

## Template Links

### Metadata of an Instagram account

Replace `USER_ID` with the numeric ID of the Instagram account to retrieve its metadata via the private API.

```
https://i.instagram.com/api/v1/users/USER_ID/info/
```

> **IMPORTANT!** You must change your browser's user agent to a mobile phone user agent before using this endpoint. Use this Chrome extension: [User-Agent Switcher and Manager](https://chromewebstore.google.com/detail/user-agent-switcher-and-m/bhchdcejhohfmigjafbampogmaanbfkg) — make sure you select a user agent for **Android** devices while navigating Instagram.

---

### Metadata of a GitHub account

Returns a list of commits from a user's repository, which may include the author's name, email, and timestamps.

```
https://api.github.com/repos/USERNAME/USERNAME/commits
```

