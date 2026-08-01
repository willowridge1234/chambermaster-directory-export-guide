# How to export a ChamberMaster or GrowthZone member directory

[ChamberMaster](https://www.growthzone.com/chambermaster) is GrowthZone's chamber-management platform. Chambers use it to manage member records and publish searchable business directories on their websites. Those are two different surfaces: the chamber's private back office can contain far more information than its public directory shows.

That distinction determines the honest answer to “How do I export a ChamberMaster member directory?”

- **If you are authorized chamber staff:** use your own ChamberMaster reporting, backup, and download tools. GrowthZone's current [ChamberMaster package comparison](https://www.growthzone.com/chambermaster-memberzone-packages) lists member statistics and reports, member-directory reports, custom report filters, and data backup/download options. Those logged-in tools operate on your chamber's own records and may include non-public fields.
- **If you are a logged-out visitor:** you do not have access to that native admin export. You can only work with the fields the chamber deliberately publishes in its public business directory, subject to that chamber's rules. A public listing is not a view of the chamber's database.

This guide is for that second situation: a public ChamberMaster/GrowthZone directory with no download offered to visitors. It explains how to scope a defensible export, interpret the visible fields, preserve provenance, and clean the result without crossing into a member-only or staff-only area.

For a broader comparison of association platforms, see [chamber-association-lead-lists](https://github.com/willowridge1234/chamber-association-lead-lists). Focused sibling guides cover [MemberClicks](https://github.com/willowridge1234/memberclicks-directory-export-guide), [Wild Apricot](https://github.com/willowridge1234/wild-apricot-directory-export-guide), and [MembershipWorks](https://github.com/willowridge1234/membershipworks-member-directory-export-guide).

**Commercial disclosure:** Rook Data Tools publishes a paid ChamberMaster/GrowthZone directory actor on Apify. It is our product, not an independent recommendation. It is linked exactly once in “Where the actor fits.” The rest of this guide is useful whether you ask the chamber for a file, copy a small directory by hand, or use any suitable tool.

## Start with authority, not software

### You administer the chamber's own account

Use the native back office. GrowthZone publicly documents that ChamberMaster plans include website-listing data, member reports, directory reports, custom report filters, and backup/download options. That route is appropriate for an authorized administrator because it can reflect the chamber's full internal record and the fields needed for the chamber's own operations.

Do not assume the public directory is a sufficient backup of your database. Public display choices can omit internal contacts, custom fields, account history, billing details, membership status details, and other operational data. If you need help choosing the correct native report or download for your plan and permissions, use GrowthZone support rather than reconstructing your own data from the public site.

### You are browsing without a login

The public business directory is a publication chosen by the chamber, not an admin export feature. GrowthZone describes ChamberMaster directories as searchable by category, representative, location, and keyword, with individual member information pages. Its current product page also describes profiles with categories, logos, descriptions, special offers, job postings, and multi-location listings.

As an outside visitor, you should not expect a button that exports the chamber's underlying membership records. Your legitimate options are:

1. Ask the chamber for a file or introduction when your purpose warrants it.
2. Use a roster, PDF, or download the chamber already offers publicly.
3. If neither exists, collect only the directory fields visible to an ordinary logged-out visitor, when the chamber's terms and access rules allow it.

Nothing in option 3 grants access to the chamber's back office, Member Information Center, or any member-only lookup.

## Confirm what is actually public

Test the directory in a signed-out browser. A field is public for this guide only if an ordinary visitor can see it without an account, invitation, payment, or access-control bypass.

GrowthZone's current directory documentation makes clear that publication is configurable. A chamber can choose whether a directory is available publicly, create multiple directories, select categories, set ordering, and assign different listing levels. Its [directory display settings documentation](https://helpdesk.growthzone.com/hc/en-us/articles/45935951532571-Setup-Directory-Display-Settings) says administrators can choose which contact details and custom fields appear, whether additional contacts appear, and whether a listing includes a logo, map, gallery, video, membership type, highlights, or description. Members with the necessary permissions can also update eligible listing information through the private Info Hub, according to GrowthZone's [listing-update documentation](https://helpdesk.growthzone.com/hc/en-us/articles/45934802764955-Update-Directory-Listing-Information-in-the-Info-Hub).

The consequence is simple: two ChamberMaster/GrowthZone directories can expose very different record shapes. Absence from the public page means “not published here,” not “the chamber does not have it.”

## Fields a public business listing may show

Depending on the chamber's configuration and the member's listing level, a logged-out visitor may see:

- business or member display name;
- business category or categories;
- public phone number and email address, when selected for display;
- street address, city, region, postal code, and map information;
- website and social-profile links;
- short and full business descriptions;
- logo, images, video, highlights, or keywords represented in the listing;
- one or more locations;
- public representatives or related contacts, when configured to appear;
- links to public jobs, deals, or other member content;
- the listing's public page URL.

Do not infer internal membership status, dues, account history, private contact details, revenue, headcount, purchasing authority, budget, or buying intent. Chamber membership is an affiliation signal, not evidence that a business needs your product now.

## Business, location, and representative are not the same record

ChamberMaster supports businesses in multiple categories, member information pages, representative information, and multi-location listings. Decide your list unit before collection:

- Use **one row per business** for account-level research.
- Use **one row per location** when territory, service area, or branch outreach matters.
- Use **one row per publicly listed representative** only when person-level analysis is necessary and appropriate.

Do not silently collapse branches because they share a domain, and do not inflate one business into several prospects merely because multiple representatives appear. Preserve the parent business and source listing so those relationships remain reviewable.

## Respect the chamber's rules

Public visibility is necessary, but it is not blanket permission for every reuse.

- Read the specific chamber's terms of use and privacy notice before collecting.
- Check that site's `robots.txt` and respect it. The [Robots Exclusion Protocol](https://www.rfc-editor.org/rfc/rfc9309.html) is a crawler-preference standard, not a grant of legal permission.
- Keep automated request volume conservative and stop when the site signals errors, rate limits, blocking, or strain.
- Never sign in, borrow credentials, create a member account to reach hidden data, defeat a bot challenge, or work around an access control.
- Collect only fields needed for the stated purpose and secure the resulting file.
- Treat marketing compliance as a separate question. A public business email or phone number is not automatic consent to bulk outreach.

GrowthZone's [privacy policy](https://www.growthzone.com/privacy-policy) covers GrowthZone and ChamberMaster as the software provider and explains how it processes account and profile data. The chamber operating a particular directory also has its own policies and responsibilities. Read the chamber's rules for the chamber's publication; do not mistake the vendor's policy for a universal permission governing every customer directory.

## Preserve provenance before cleaning

For every row, retain:

- the displayed values exactly as published;
- the public listing URL, or the directory page URL if no individual page is offered;
- the chamber name and public site domain;
- the category or search context in which the record appeared;
- the collection date and time;
- whether the row represents a business, location, or representative.

Keep raw and cleaned columns separate. If a chamber later changes a category, removes a listing, or corrects a phone number, provenance explains why your snapshot differs.

## Clean and deduplicate without inventing facts

Normalize whitespace, capitalization, phone formatting, and website domains for comparison, but retain the raw text. Group likely duplicates for human review using several signals together:

- same normalized business name and phone;
- same domain plus a compatible name or address;
- same address plus a compatible name;
- an explicit parent/branch or business/representative relationship in the listing.

A shared domain alone can connect separate branches, franchises, or related contacts. A shared phone can be a switchboard. Similar names can belong to unrelated companies. Flag ambiguity; do not force a merge.

The companion [cross-platform guide's cleaning section](https://github.com/willowridge1234/chamber-association-lead-lists#how-to-clean-and-deduplicate-a-directory-sourced-list) goes deeper on account-versus-location decisions and conflict handling.

## When automation is the wrong choice

Do not automate when:

- the directory or needed fields require a login;
- the chamber's terms, `robots.txt`, or direct instructions prohibit the intended activity;
- a small list can be reviewed accurately by hand;
- the chamber already offers the right download;
- you need private, verified, or current facts the public listing cannot establish;
- the chamber has asked you to stop.

Automation can reduce repetitive work on a genuinely public directory. It is not a workaround for missing authority.

## Where the actor fits

After confirming that a directory is publicly reachable without login and that collection is consistent with the chamber's own rules, our [ChamberMaster & GrowthZone Directory Scraper](https://apify.com/rook-data-tools/chambermaster-directory-scraper?utm_source=github&utm_medium=referral&utm_campaign=chambermaster-member-directory-export-guide) converts the visible public business listings into structured records.

The current public actor description lists outcome fields including business name, category, phone, website, address, social profiles, and description. Results are available through Apify in structured export formats. It is designed only for public directory content; it is not an admin export and does not make private chamber data public.

**Live pricing and adoption snapshot, verified August 1, 2026:** the actor uses Apify's pay-per-event model at **$0.005 per run start plus $0.005 per business record saved**. The live actor record showed **21 lifetime runs, 1 total user, 0 reviews, a 0 rating, and 0 bookmarks**. Those are small numbers, and `totalUsers: 1` does not establish any third-party adoption. Run a small test against a directory you understand and judge the output directly. Pricing and statistics can change, so check the listing before use.

We do not publish the actor's collection method. This guide describes scope, visible outcome fields, quality checks, and responsible use—not a replication recipe.

## Final checklist

- [ ] I know whether I am an authorized administrator or a logged-out visitor.
- [ ] If I am the administrator, I checked native ChamberMaster reports and downloads first.
- [ ] If I am an outside visitor, every field is visible without login.
- [ ] I checked the chamber's own terms, privacy notice, and `robots.txt`.
- [ ] I defined whether each row represents a business, location, or representative.
- [ ] I preserved raw values, source URL, chamber, category context, and collection time.
- [ ] I will review duplicate candidates instead of merging on one weak signal.
- [ ] I will not infer private operational facts or current buying intent.
- [ ] I have a conservative stop condition for errors, blocking, or site strain.

## Frequently asked questions

### Can a chamber administrator export its own ChamberMaster member data?

Yes. GrowthZone's current ChamberMaster package materials list member and directory reporting, custom report filters, and data backup/download options. Those are authenticated back-office capabilities for the chamber's own authorized users, not public-directory features.

### Can a public visitor use that same export?

No. A logged-out visitor sees only the chamber's published directory. Unless the chamber separately offers a download, the visitor has no right or route to the native admin export and must not treat public listings as the full member database.

### What information can a ChamberMaster business directory display?

The chamber controls it. Current GrowthZone documentation supports names, categories, selected contact details, custom directory fields, descriptions, logos, maps, galleries, video, highlights, membership type, additional contacts, and public member content. Actual directories may show only a subset.

### Are ChamberMaster and GrowthZone the same thing?

ChamberMaster is a chamber-focused product offered by GrowthZone. Public directory pages and support materials may use ChamberMaster, MemberZone, or GrowthZone branding depending on the product and configuration. Identify the platform from visible evidence; if that evidence is inconclusive, label it unknown.

### Is it legal to export a public directory?

There is no universal answer, and this guide is not legal advice. Public access does not override site terms, privacy law, marketing law, or restrictions on reuse. Staying outside every login, respecting site rules and `robots.txt`, minimizing collection, and using conservative request volume are baseline safeguards. Seek legal advice for high-risk or large-scale use.

## The useful standard

A good ChamberMaster/GrowthZone directory export is not the largest file you can obtain. It is a traceable, purpose-limited snapshot of fields the chamber deliberately showed to logged-out visitors, kept separate from the chamber's private admin data and honest about what membership does—and does not—prove.

## Related

- [chamber-association-lead-lists](https://github.com/willowridge1234/chamber-association-lead-lists) — Cross-platform guide to chamber and association directory leads
- [memberclicks-directory-export-guide](https://github.com/willowridge1234/memberclicks-directory-export-guide) — Focused MemberClicks directory guide
- [wild-apricot-directory-export-guide](https://github.com/willowridge1234/wild-apricot-directory-export-guide) — Focused Wild Apricot directory guide
- [membershipworks-member-directory-export-guide](https://github.com/willowridge1234/membershipworks-member-directory-export-guide) — Focused MembershipWorks directory guide
