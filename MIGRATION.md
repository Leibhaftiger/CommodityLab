# Migration: WSL2 → Native Windows

**Status: complete.** This repo is a publish target, not a runnable app — there's
no venv or dependencies to set up.

## What happened (2026-08-16)

- Two regenerated report files (`commodities_report_de_latest.html`,
  `commodities_report_en_latest.html`) that were sitting modified in the WSL working
  tree were committed and pushed first (`chore: update generated commodity
  reports`), so nothing was lost.
- Repo then cloned fresh to `C:\own\python_proj\commoditylab`.
- This repo only ever holds generated HTML reports pushed here by
  `Commodities_Analyzer/publish_reports.sh` — it's not meant to be edited directly.

## Still needed

- [ ] `Commodities_Analyzer/publish_reports.sh` clones/pulls/pushes into this folder
      using a **WSL-relative path** (`$HOME/python_proj/commoditylab`). If
      `publish_reports.sh` is going to be run from the Windows copy of
      `Commodities_Analyzer` going forward, update that path to the Windows location
      (`C:\own\python_proj\commoditylab`) first — otherwise it will keep publishing
      to the WSL copy only, and this Windows clone will silently go stale.
