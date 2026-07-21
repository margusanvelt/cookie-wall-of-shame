# Dark Pattern EU

A wall of shame for deceptive cookie consent banners across the EU.

Cookie consent should be a genuine choice. Instead, many websites deploy manipulative interfaces — known as dark patterns — to nudge users into giving up their privacy. This project documents and exposes these practices to hold companies accountable and raise public awareness.

## Why This Matters

Under EU law, valid consent must be **freely given, specific, informed, and unambiguous** ([GDPR Art. 7](https://eur-lex.europa.eu/eli/reg/2016/679/oj#d1e2001-1-1)). The [ePrivacy Directive (2002/58/EC)](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32002L0058) further requires informed consent before storing cookies on a user's device. Dark patterns undermine both by manufacturing consent that doesn't meet the legal standard.

Enforcement bodies like the [EDPB](https://www.edpb.europa.eu/), [CNIL](https://www.cnil.fr/en), and [noyb](https://noyb.eu/) have repeatedly ruled that these deceptive designs violate EU data protection law.

### Key Legal References

| Document | Link |
|---|---|
| General Data Protection Regulation (GDPR) | [Regulation (EU) 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj) |
| ePrivacy Directive | [Directive 2002/58/EC](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32002L0058) |
| EDPB Guidelines on consent (05/2020) | [Guidelines 05/2020](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-052020-consent-under-regulation-2016679_en) |
| EDPB Report on cookie banners (2023) | [Cookie Banner Taskforce Report](https://www.edpb.europa.eu/our-work-tools/our-documents/report/report-work-undertaken-cookie-banner-taskforce_en) |

## How It Works

This is a single static HTML page hosted on GitHub Pages. No build step, no dependencies. The data lives directly in the `<table>` inside `index.html`.

## Pattern Types

| Pattern | Description | Why It Violates EU Law |
|---|---|---|
| **Hidden Reject** | The reject option is buried in sub-menus or settings | Consent is not freely given if refusing is significantly harder than accepting ([EDPB Guidelines 05/2020, para. 46](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-052020-consent-under-regulation-2016679_en)) |
| **Asymmetric Buttons** | "Accept" is prominent; reject is a tiny text link | Creates an imbalance that fails the "freely given" requirement |
| **Pre-ticked Boxes** | Consent checkboxes are checked by default | Explicitly prohibited — the CJEU ruled in *Planet49* (C-673/17) that pre-ticked boxes do not constitute valid consent |
| **Confusing Language** | Misleading wording to trick users into accepting | Consent must be informed and unambiguous (GDPR Art. 4(11)) |
| **Forced Action** | No way to use the site without accepting all cookies | Cookie walls generally violate GDPR unless strictly necessary cookies are the only alternative ([EDPB Guidelines 05/2020, para. 39](https://www.edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-052020-consent-under-regulation-2016679_en)) |
| **Nagging** | Repeated prompts to accept after the user has declined | Undermines the durability of refusal and pressures consent |

## Contributing

1. Fork this repo
2. Edit `index.html`
3. Copy an existing `<tr>` row in the table
4. Fill in the site name, URL, mark violations with `✕`, add a short description and date
5. Open a pull request

### Row Format

```html
<tr>
  <td class="name"><a href="https://example.com" target="_blank" rel="noopener">Example</a></td>
  <td class="check"><span class="yes" aria-label="Yes">✕</span></td>  <!-- Hidden Reject -->
  <td class="check"></td>                                               <!-- Asymmetric Buttons -->
  <td class="check"></td>                                               <!-- Pre-ticked Boxes -->
  <td class="check"></td>                                               <!-- Confusing Language -->
  <td class="check"></td>                                               <!-- Forced Action -->
  <td class="check"></td>                                               <!-- Nagging -->
  <td class="description">Short factual description of the dark pattern.</td>
  <td class="date">2026-07-21</td>
</tr>
```

### Guidelines

- One row per website
- Mark each applicable violation with `✕`, leave others empty
- Descriptions should be factual and specific — state what you see, not opinions
- Screenshots in `assets/img/` are welcome but not required

## Running Locally

Open `index.html` in a browser. That's it.

## License

MIT
