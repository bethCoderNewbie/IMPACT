# IT Admin Validation — SharePoint, Shared Mailbox & Power Automate
**Date:** 2026-03-05
**Purpose:** Validate what Operations can do independently vs. what requires IT, based on Microsoft official documentation.

---

## 1. The Shared Mailbox Password — Bigger Issue Than Expected

Microsoft's official guidance is clear: **shared mailboxes are not meant to be logged into directly.** The password is system-generated and Microsoft recommends keeping direct sign-in **blocked**.

> "Always block sign-in for the shared mailbox account and keep it blocked."
> — [Microsoft Learn: About Shared Mailboxes](https://learn.microsoft.com/en-us/microsoft-365/admin/email/about-shared-mailboxes?view=o365-worldwide)

**What this means for IMPACT:**
If Ops is currently logging in directly with the `barton.impact@wichita.edu` password, that is not the supported method. The correct setup is:

- Each Ops member keeps their own account (`@wichita.edu`)
- IT grants them **"Send As" or "Full Access" delegation** to the shared mailbox
- They send from `barton.impact@wichita.edu` through their own login — no shared password needed

---

## 2. Power Automate — Ops Can Do This Without IT (Mostly)

For basic automation (sending emails from the shared mailbox), **Ops can set this up themselves** inside Power Automate:

1. In any Power Automate flow, use the Outlook connector → "Send an email" action
2. Open advanced settings → select **"Other mailbox"** in the "Send from" field
3. Enter `barton.impact@wichita.edu` as the send-from address
4. Authenticate with your own Ops account

**IT is only needed** if the flow requires application-level OAuth — for example, reading incoming emails programmatically or running flows with no user logged in. That requires IT to register an app in Azure AD.

---

## 3. SharePoint Site Creation & Hub Association — Revised Structure

Microsoft confirms a two-step unlock model that releases ongoing Hub association control to Ops after a single IT setup.

> "When creating a hub site, SharePoint Administrators can allow only certain site owners to associate sites with the hub. After a SharePoint Administrator gives a site owner permission, the site owner can then associate sites themselves."
> — [Microsoft Support: Associate a SharePoint site with a hub site](https://support.microsoft.com/en-us/office/associate-a-sharepoint-site-with-a-hub-site-ae0009fd-af04-4d3d-917d-88edb43efc05)

> "Site admins have permission to manage sites, but they don't need to have an admin role in Microsoft 365."
> — [Microsoft Learn: Manage Site Admins](https://learn.microsoft.com/en-us/sharepoint/manage-site-collection-administrators)

| What Ops Needs to Do | Admin Level Required | Who Does It | When |
|---|---|---|---|
| Create a basic Team Site | None — any M365 user | Ops | Anytime |
| Manage site members and permissions | **Site Collection Admin** per site | Ops — after IT assigns role | Ongoing, self-service |
| Register the IMPACT Hub | **SharePoint Admin** (tenant-level) | IT only | One-time at setup |
| Grant Ops permission to associate sites to Hub | **SharePoint Admin** (tenant-level) | IT only | One-time at setup — set inside Hub settings |
| Connect new project sites to the Hub | **Hub Site Owner** (delegated) | **Ops** | Ongoing — no IT ticket needed |

**The handover is a two-step unlock — IT does both once at setup, then steps back:**
1. IT registers the Hub and sets "who can associate sites" to include Ops
2. IT assigns Ops as Site Collection Admin per site at creation

After those two actions, **Ops runs everything day-to-day without IT.**

---

## 4. Revised Responsibility Summary

| Task | Can Ops Do It? | What IT Needs to Do Once |
|---|---|---|
| Send email as `barton.impact@wichita.edu` | Yes — via delegation, not shared password | Grant Ops "Send As" access to the mailbox |
| Run Power Automate flows to send emails | Yes — using their own login + Send As | Nothing extra needed for basic flows |
| Create team sites (Level 3) | Yes — from SharePoint start page | Nothing needed |
| Manage site members and permissions | Yes — after IT assigns Site Collection Admin role | Assign Site Collection Admin per site |
| Register the IMPACT Hub | No | IT must do this — one-time, permanent |
| Connect new sites to the Hub | **Yes** — after IT grants Hub association permission | Grant Ops Hub association rights at setup |
| Advanced OAuth / automated email reading | No | IT must register an Azure AD app |

---

## 5. Action Items for Next Steps

| Action | Owner | Notes |
|---|---|---|
| Stop direct login to `barton.impact@wichita.edu` | Ops + IT | Switch to delegated "Send As" access per user |
| IT grants "Send As" delegation to Ops members | IT Admin | One-time setup per Ops member |
| IT registers the IMPACT Hub at tenant level | IT Admin | Required to enable Hub-and-Spoke architecture |
| IT sets Ops as allowed Hub associators inside Hub settings | IT Admin | One-time — unlocks Ops to connect sites to Hub independently |
| IT assigns Site Collection Admin role to Ops per site | IT Admin | One-time per site at creation |
| Ops connects new project sites to Hub as needed | Operations | Self-service after IT unlock |
| Ops sets up Power Automate flows using Send As method | Operations | No IT involvement needed for basic email flows |
| Evaluate if automated email reading is needed | Leadership + Ops | If yes, IT must register an Azure AD app |

---

## Sources

- [About Shared Mailboxes in Microsoft 365](https://learn.microsoft.com/en-us/microsoft-365/admin/email/about-shared-mailboxes?view=o365-worldwide)
- [Connect to Power Automate with shared mailbox](https://learn.microsoft.com/en-us/answers/questions/1518901/connect-to-power-automate-with-shared-mailbox)
- [Use a shared Outlook mailbox in email automations - Power Automate](https://learn.microsoft.com/en-us/power-automate/desktop-flows/how-to/outlook-shared-mailbox)
- [Manage site admins - SharePoint in Microsoft 365](https://learn.microsoft.com/en-us/sharepoint/manage-site-collection-administrators)
- [Create a site - SharePoint in Microsoft 365](https://learn.microsoft.com/en-us/sharepoint/create-site-collection)
- [About the SharePoint Administrator role in Microsoft 365](https://learn.microsoft.com/en-us/sharepoint/sharepoint-admin-role)
- [Associate a SharePoint site with a hub site](https://support.microsoft.com/en-us/office/associate-a-sharepoint-site-with-a-hub-site-ae0009fd-af04-4d3d-917d-88edb43efc05)
- [Create a hub site in SharePoint](https://learn.microsoft.com/en-us/sharepoint/create-hub-site)
- [Planning your SharePoint hub sites](https://learn.microsoft.com/en-us/sharepoint/planning-hub-sites)
