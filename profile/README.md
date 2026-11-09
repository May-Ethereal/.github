<!--
  This file renders on https://github.com/May-Ethereal as the org landing page.
-->

<h1 align="center">Ethereal</h1>

<p align="center">
  <strong>Game reversal and security analytics, Tokyo.</strong><br>
  <em>We take games apart to understand how they really work, then build tooling on what we find.</em>
</p>

<p align="center">
  <a href="https://ethereal.tokyo/">Website</a> ·
  <a href="https://github.com/May-Ethereal">GitHub</a> ·
  <a href="https://github.com/May-Ethereal/.github/blob/main/CONTRIBUTING.md">Contribute</a>
</p>

---

## About

Ethereal is a small team in Japan working on game reversal, console kernel
research, and the tooling that grows out of it. We work from disassembly,
traces and reproducible experiments, and we only make claims we can back with
evidence we can show.

The work runs on two tracks that are kept deliberately separate:

**Open research and tooling — public repositories.**

- [afterglow-web](https://github.com/May-Ethereal/afterglow-web) — a PS4
  WebKit kernel exploit that runs from the console's own browser and deploys a
  homebrew environment on firmware 12.00 through 14.00.
- [ImGui-Menu-Ethereal](https://github.com/May-Ethereal/ImGui-Menu-Ethereal) — our
  fork of the ImGui menu layer used by our internal tooling, tracking upstream
  and carrying our own changes.
- [May-Ethereal-Skills](https://github.com/May-Ethereal/May-Ethereal-Skills) — the
  agent skills that encode our research workflows.

**Commercial tooling — private repositories, shipped to licensed customers.**

Our product line — a Windows loader with a licensing panel, a customer-facing
API, and the release pipeline behind them — is developed in private
repositories and delivered only to licensed customers under NDA. Public
repositories contain none of that code, and the loader binaries are not
redistributable. The website at
[ethereal.tokyo](https://ethereal.tokyo/) describes the product; this page
describes the people behind it.

## What we do

- **Binary analysis** — disassembly and decompilation of game executables and
  native modules (IDA Pro, Ghidra, Binary Ninja).
- **Format research** — reverse engineering proprietary archive, asset, model
  and save formats, with specs and parsers.
- **Runtime instrumentation** — hooking, tracing and debugging to map behavior
  that static analysis alone cannot reach.
- **Kernel and firmware research** — console kernel exploitation chains and
  homebrew environment deployment.
- **Product engineering** — the loader, licensing panel, and API that ship to
  licensed customers, with signed releases and a fail-closed deploy path.

## Toolbox

`IDA Pro` · `Ghidra` · `Binary Ninja` · `x64dbg` · `Frida` · `Cheat Engine`
· `C/C++` · `Rust` · `Python` · `x86/x64 & ARM asm`

## Projects

| Repository | What it is | Visibility |
| --- | --- | --- |
| [afterglow-web](https://github.com/May-Ethereal/afterglow-web) | PS4 WebKit kernel exploit and homebrew-environment deployment, run from the console browser | Public |
| [ImGui-Menu-Ethereal](https://github.com/May-Ethereal/ImGui-Menu-Ethereal) | Fork of the ImGui menu layer used in our tooling, tracking upstream | Public |
| [May-Ethereal-Skills](https://github.com/May-Ethereal/May-Ethereal-Skills) | Agent skills for our reverse-engineering and console-research workflows | Private |
| [ethereal.tokyo](https://github.com/May-Ethereal/ethereal.tokyo) | The website and the product infrastructure behind it | Private |
| Loader, panel and API | The licensed product line, developed and shipped privately | Private |

Browse the full list on the
[organization repositories page](https://github.com/orgs/May-Ethereal/repositories).

## Scope and ethics

We publish work for hardware and software the reader owns: analysis notes,
format specifications, and tooling that runs on the user's own console. We do
**not** publish anti-cheat evasion, credential tooling, or anything aimed at
harming other players or publishers, and we do not redistribute game binaries,
keys or proprietary assets. Customer-facing tooling stays in private
repositories and reaches customers only under NDA.

Respect the laws of your jurisdiction and the terms of the software you study.

## Get involved

- 📖 Read the [Contributing guide](https://github.com/May-Ethereal/.github/blob/main/CONTRIBUTING.md)
- 🤝 Review the [Code of Conduct](https://github.com/May-Ethereal/.github/blob/main/CODE_OF_CONDUCT.md)
- 🏛️ See how we're run in [Governance](https://github.com/May-Ethereal/.github/blob/main/GOVERNANCE.md)
- 🔐 Report security issues via our [Security policy](https://github.com/May-Ethereal/.github/blob/main/SECURITY.md)

## Contact

- Web: <https://ethereal.tokyo/>
- Maintainers: [@AtsuageZ](https://github.com/AtsuageZ) · [@NetVar1337](https://github.com/NetVar1337)
