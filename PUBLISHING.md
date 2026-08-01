# Publication metadata and checks

This is the exact handoff for the routed Codex-desktop browser session. The guide is complete
locally; publication has not occurred from this box. A push with the new, not-yet-registered
deploy key was attempted after the local commit and failed with `Permission denied
(publickey)`, as expected before repository creation and key registration. No external branch
was created or changed.

- Repository: `willowridge1234/chambermaster-directory-export-guide`
- Visibility: public
- Default branch: `main`
- Description: `How to export a public ChamberMaster or GrowthZone member directory: admin vs public data, provenance, deduplication, and responsible use.`
- Topics: `chambermaster`, `growthzone`, `chamber-of-commerce`, `member-directory`,
  `association-management`, `data-export`, `public-data`, `b2b-sales`
- Website: leave blank; the README contains the single disclosed actor link

Local repository: `/home/income/repo/guide-chambermaster-directory-export/`.

## Verified publication capability gap

On 2026-08-01 at 18:48:56 UTC, anonymous `GET
https://api.github.com/repos/willowridge1234/chambermaster-directory-export-guide` returned HTTP
404 with GitHub request ID `8A5A:65A0D:7FFB62:1BFD0F7:6A6E3F98`, confirming that the name was
free at that time and no duplicate public repository existed.

This box has no `gh` CLI, `GITHUB_TOKEN`, `GH_TOKEN`, `.netrc`, or configured credential helper.
Its existing SSH identity authenticates only as the repository-scoped deploy key
`willowridge1234/rook-income-tools`, so it cannot create this repository. A brand-new ED25519
keypair was generated solely for this guide:

- Private key: `/home/income/.ssh/chambermaster-directory-export-guide` (mode 0600; never paste
  it into GitHub or copy it off the droplet)
- Public key: `/home/income/.ssh/chambermaster-directory-export-guide.pub`
- Fingerprint: `SHA256:x3VMNai00aDCeLEDAInNuy0E8LQt4r3qHDpRRfcu7XU`

## Exact desktop publication procedure

1. Signed in to GitHub as `willowridge1234`, open `https://github.com/new`.
2. Create a repository named `chambermaster-directory-export-guide` under
   `willowridge1234`. Set it to **Public**. Do **not** initialize it with a README,
   `.gitignore`, or license. Apply the description above and leave Website blank.
3. Add the eight topics listed above.
4. Open the new repository's **Settings → Deploy keys → Add deploy key**. Use the title
   `chambermaster-directory-export-guide publisher`. On the droplet, display and copy only
   the public key with:

   ```bash
   cat /home/income/.ssh/chambermaster-directory-export-guide.pub
   ```

   Paste that public key, enable **Allow write access**, and add it. Never display or paste
   the private key.
5. Publish the existing reviewed local commit without modifying or re-initializing it:

   ```bash
   git -C /home/income/repo/guide-chambermaster-directory-export remote add origin git@github.com:willowridge1234/chambermaster-directory-export-guide.git
   GIT_SSH_COMMAND='ssh -i /home/income/.ssh/chambermaster-directory-export-guide -o IdentitiesOnly=yes' git -C /home/income/repo/guide-chambermaster-directory-export push -u origin main
   ```

   `origin` already exists from the failed publication attempt. Verify it exactly with
   `git -C /home/income/repo/guide-chambermaster-directory-export remote -v` and run only the
   `GIT_SSH_COMMAND=... git ... push` command above. Never force-push.
6. Perform every anonymous check below. Publication is successful only after the branch and
   public files are confirmed. If creation or push has an ambiguous result, mark the external
   effect `uncertain`; do not retry blindly.

## Anonymous post-publication verification

1. `https://github.com/willowridge1234/chambermaster-directory-export-guide` returns HTTP 200.
2. Anonymous `GET
   https://api.github.com/repos/willowridge1234/chambermaster-directory-export-guide` reports
   `"private": false`, `"default_branch": "main"`, and the exact description/topics above.
3. Raw public `README.md`, `LICENSE`, and `PUBLISHING.md` match the committed local files
   byte-for-byte.
4. The README contains the exact tagged actor URL once and only once:
   `https://apify.com/rook-data-tools/chambermaster-directory-scraper?utm_source=github&utm_medium=referral&utm_campaign=chambermaster-member-directory-export-guide`.
5. Every README link resolves, including the cited GrowthZone product, package, support, and
   privacy pages and all four related GitHub guides.
6. Anonymous `GET
   https://api.apify.com/v2/acts/rook-data-tools~chambermaster-directory-scraper` still reports
   `"isPublic": true`. Compare its active pricing and stats with the dated snapshot in the
   README; later changes are not publication defects, but should not be misrepresented.
7. Confirm the public README contains no selector, collection endpoint, actor-bound request,
   source-identification recipe, access-control bypass, secret-method framing, credentials,
   private data, or real-person sample data.

## Publish the related-guide cross-links

The new link was also committed locally in all sibling READMEs. These public repositories must
be fast-forwarded through the routed GitHub integration because this box has no usable write
credential for them:

- `willowridge1234/memberclicks-directory-export-guide`: local commit `15eed07` changes only
  `README.md`.
- `willowridge1234/wild-apricot-directory-export-guide`: local commit `ede8ffa` changes only
  `README.md`.
- `willowridge1234/membershipworks-member-directory-export-guide`: local commit `13c126b`
  changes only `README.md`.

For each repository, fetch its public `main`, create a UTF-8 blob from that local README, create
a tree replacing only `README.md` while preserving every other public path, create one commit
whose sole parent is the current public `main`, and fast-forward `refs/heads/main` with force
disabled. Use commit message `Link ChamberMaster directory export guide`. Do not overwrite
unrelated live changes: if a local README does not contain them, reconcile them before creating
the tree.

Afterward, anonymously fetch each raw public README and confirm it matches its committed local
file after normalizing CRLF to LF. In each, verify the new link points to
`https://github.com/willowridge1234/chambermaster-directory-export-guide`. The broad
`chamber-association-lead-lists` cross-link is tracked in the main `/home/income/repo` commit and
will publish with that repository's normal push.

## Facts verified for this guide on 2026-08-01

- ChamberMaster positioning and profile capabilities: GrowthZone's current ChamberMaster
  product page, `https://www.growthzone.com/chambermaster`.
- Native authorized-admin capabilities (member and directory reports, custom report filters,
  backup/download options) and public business-directory capabilities: GrowthZone's current
  ChamberMaster/MemberZone package comparison,
  `https://www.growthzone.com/chambermaster-memberzone-packages`.
- Configurable public-directory display fields and listing levels: GrowthZone Support,
  `https://helpdesk.growthzone.com/hc/en-us/articles/45935951532571-Setup-Directory-Display-Settings`.
- Member editing of eligible listing fields through the authenticated Info Hub: GrowthZone
  Support,
  `https://helpdesk.growthzone.com/hc/en-us/articles/45934802764955-Update-Directory-Listing-Information-in-the-Info-Hub`.
- Vendor privacy scope: GrowthZone's current privacy policy,
  `https://www.growthzone.com/privacy-policy`.
- Actor identity, public status, active pay-per-event pricing, outcome fields, and statistics:
  live authoritative `GET
  https://api.apify.com/v2/acts/rook-data-tools~chambermaster-directory-scraper`, not the cached
  Apify Store search index. The active pricing entry started 2026-07-31 and showed $0.005 per
  start plus $0.005 per saved business record. Stats at verification were 21 total runs, 1
  total user, 0 reviews, 0 rating, and 0 bookmarks.

No platform factual claim in the README was copied from a sibling or broad guide without fresh
verification against GrowthZone's current public pages. No acquisition method was documented.
