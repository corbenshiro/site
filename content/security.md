+++
title = "Security of this Site"
description = "An article that delves into the security model of this site."
date = 2023-08-31
draft = false

[taxonomies]
categories = ["Technology"]
tags = ["Cybersecurity"]
[extra]
toc = true
keywords = "GnuPG, OpenSSH, Git"
+++

## Authenticity

As of August 2023 all Git commits belonging to me are PGP-signed by my private Ed25519 subkey (certified via my master Ed25519 key). They are also pushed over SSH and authenticated by the very same subkey. I use the gpg-agent daemon to manage all of my keys.

Whilst an issued TLS certificate associated with its respective website (e.g. HTTPS) is usually enough for authenticity (e.g. preventing MITM attacks), it does not mitigate comprehensive attack vectors such as mistakenly issued certificates and CA breaching (server-side), and certificate store poisoning (client-side).

Still, most browsers don't have pinned certificates, nor do many servers support key pinning. The modern web is built upon trusted roots; whilst it does have its downsides, it does however prevent sysadmins from any potential misconfiguration of their key pinning.

Due to the aformentioned, I implore you to verify this website (contents of [/](/)) and any of my other wares using the information provided.

Get the public keypair to my commit signing/pushing subkey:
- [/corbenshiro.asc](/corbenshiro.asc)
- [github.com/corbenshiro.gpg](https://github.com/corbenshiro.gpg)
- [codeberg.org/corbenite.gpg](https://codeberg.org/corbenite.gpg)

Cross-reference against my fingerprints:
- [corbenite.codeberg.page/fpr.txt](https://corbenite.codeberg.page/fpr.txt)
  - [corbenite.codeberg.page/subfpr.txt](https://corbenite.codeberg.page/subfpr.txt)
- [cdredge.neocities.org/fpr.txt](https://cdredge.neocities.org/fpr.txt)
  - [cdredge.neocities.org/subfpr.txt](https://cdredge.neocities.org/subfpr.txt)
- [cdredge.surge.sh/fpr.txt](https://cdredge.surge.sh/fpr.txt)
  - [cdredge.surge.sh/subfpr.txt](https://cdredge.surge.sh/subfpr.txt)

```
pub   ed25519 2023-08-31 [C]
      CD9B FF15 C79C 2D0F 533F  682E CB01 EBA8 B48F 7A2A
```

```
sub   ed25519 2023-08-31 [S]
      E1F4 B46A ED84 1C40 3ADD  1090 2BFA B105 9A58 3670
```

My public curriculum vitæ can be viewed at: [/cv-public.pdf](/cv-public.pdf)

My private curriculum vitæ (which includes my full phone no.) has a detached PGP signature which you can use to verify said CV: [/cv.pdf.asc](/cv.pdf.asc)

The OpenPGP-compliant system I personally recommend is GnuPG, if you have installed the program — refer to its manpages, if not; consult the online documentation: [gnupg.org/documentation/](https://gnupg.org/documentation/)

## Audit

If you're viewing the HTML5 version of my site, you can audit it via the [Lighthouse](https://pagespeed.web.dev/report?url=corbenshiro.github.io) tool that is bundled in Chromium-based browsers or use the URL provided. Lighthouse also supports testing with device emulation, i.e. to execute mobile mode on a desktop machine or vice versa.

Use of [YellowLabTools](https://yellowlab.tools/) and [Observatory](https://observatory.mozilla.org/analyze/corbenshiro.github.io) are recommended.
