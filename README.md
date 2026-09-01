### Data tools that report their own cost

I build small, single-purpose scrapers. Each one does a single job on public
data, and every run publishes what it actually cost to produce a thousand rows.

**Live on the Apify Store →** [apify.com/abdulwhab95](https://apify.com/abdulwhab95)

---

#### How I pick what to build

Four checks, in the order that kills a bad target fastest:

| | |
|---|---|
| **`robots.txt`** | against the exact path, not the homepage |
| **Terms of use** | a site can permit a path in robots and forbid bots in its terms — the terms win |
| **Reachability** | if it needs a browser and a proxy pool, the margin is usually already gone |
| **Unit economics** | cost per 1,000 rows measured on a real run, before publishing, not after |

Anything ambiguous gets dropped. There are millions of targets and no reason
to spend judgment on a doubtful one.

#### What the tools guarantee

- **Public data only.** `robots.txt` is read before anything else is fetched.
- **A stable shape.** Every field is always present; missing values are `null`,
  never omitted. Nothing downstream breaks on a quiet schema change.
- **A number, not a claim.** Each run writes cost, reach rate, and a
  publish/reject verdict to its own report.

#### Background

HTTP bridges, high-volume data pipelines, monitoring and alerting systems.
Kuwait.
