# What is shared, and what stays private

[Gallery](README.md) · [Catalog](CATALOG.md)

The user requested unchanged screenshots, with credential-bearing evidence kept private. This is a **public repository**. A folder named private, a hidden file, a closed pull request or a deleted branch would not provide reliable confidentiality for committed credentials.

## Not copied into this repository or its upload package

| ID | Reason |
|---|---|
| EV-012 | Recon table containing a credential; plaintext credential present in the private original. |
| EV-015 | Java/CMD table containing a credential; plaintext credential present in the private original. |
| EV-022 | Timeline view containing a credential; plaintext credential present in the private original. |
| EV-024 | Credential-bearing script-block text; plaintext credential present in the private original. |
| EV-025 | WdBoot child commands containing a credential; plaintext credential present in the private original. |

EV-048, the lengthy partial raw configuration, remains local because the relevant active definitions are shown in EV-049. EV-003 has no available original. No redactions were applied to the shared images; sensitive originals were omitted entirely. Authorized classroom review of originals must occur through a separate approved private channel.

## Scope of the review

New noah/ files only were selected and reviewed for this package. Existing repository files, Greg's directory and prior Git history were not audited for secrets, changed or certified safe by this work. The manifest identifies private originals without publishing their bytes or credential values.

## Adding evidence later

1. Keep the original outside GitHub until reviewed.
2. Check the whole image, command lines, search text, browser tabs, tooltips and backgrounds for secrets.
3. Never upload malware binaries, memory/disk images or unreviewed raw logs.
4. Preserve the EV number, source, event timezone and file hash.
5. Add a caption: what is visible, why it matters, and what it does not prove.
6. Update the catalog/manifest only after review.

.gitignore is a convenience, not a security boundary. Check the actual staged files before publishing.
