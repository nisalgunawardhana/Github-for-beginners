# How I Built GitHub for Beginners

This document walks through how this repository was designed and built, step by step, so other students can see the reasoning behind it and reuse the approach for their own projects.

## 1. Defining the problem

Most "learn Git/GitHub" tutorials teach commands in isolation (`git clone`, `git commit`, `git push`) without a real workflow to practice on. I wanted a repository where a complete beginner could:

- Fork and clone a real repo
- Make an actual change and open a real Pull Request
- Get feedback through GitHub Issues
- Walk away having done the entire GitHub flow at least once, not just read about it

So instead of writing a tutorial *about* GitHub, I built a hands-on practice repo that *is* the exercise.

## 2. Structuring the repository

I started with a minimal `README.md` and `LICENSE` (MIT, so anyone could reuse or adapt this material freely), then grew the structure as the course content grew:

```
Github-for-beginners/
├── README.md                  # Main course: setup + exercises
├── LEARN.md                    # This file
├── LICENSE
├── student-introductions.md    # Where students make their first PR
├── practice-file.md            # Extra file for branch/PR practice
├── git-commands-reference.md   # Cheat sheet
├── guides/                      # Deeper topic guides (Pages, .gitignore, merge conflicts...)
├── support md files/            # Troubleshooting docs (fork steps, Windows setup, git config issues)
├── student-opportunities/       # GitHub Student Pack perks (certification vouchers, DataCamp)
├── docs/                        # PDF prerequisites guide
├── images/                      # Screenshots used throughout the README
└── .github/
    ├── ISSUE_TEMPLATE/          # Bug report, feature request, question, submission
    └── workflows/               # Automation for reviewing submissions
```

The guiding principle: keep the root README focused on the linear "do this, then this" path, and push supporting material (deep dives, troubleshooting, extras) into subfolders so beginners aren't overwhelmed on first open.

## 3. Designing the exercise flow

I wrote the exercises in the order a real contribution actually happens, since that muscle memory is the real learning outcome:

1. **Fork** the repository into the student's own account ([support md files/fork.md](support%20md%20files/fork.md))
2. **Clone** their fork locally, with OS-specific setup notes (including a dedicated [Windows Command Prompt guide](support%20md%20files/win-cmd.md) after seeing Windows students hit the most setup friction)
3. **Branch** using a naming convention (`feature/your-name-introduction`) so every student's branch is self-descriptive
4. **Edit** `student-introductions.md` — a low-stakes, plain-text file, chosen deliberately so the first PR a student ever opens has near-zero risk of merge conflicts
5. **Stage, commit, push** — with a dedicated [Git configuration troubleshooting guide](support%20md%20files/Git-Configuration-Troubleshooting.md) added after recurring "Git doesn't recognize my name/email" issues from real students
6. **Open a Pull Request** back to the upstream repo
7. **Open an Issue** using a "Submission" template to close the loop and request review

Each step in the README links out to a focused support doc rather than inlining every edge case, keeping the main path readable.

## 4. Adding real screenshots instead of only text

Early drafts were text-only. Testing it on actual beginners, I found the PR and Issue creation steps needed a lot more clarity, so I added real screenshots (`images/pr-image1.png` → `pr-image3.png`, `images/issue1.png`, `images/issue2.png`) captured from the actual GitHub UI at each step, and embedded them directly under the relevant instructions in the README.

I also recorded full walkthrough videos (in both Sinhala and English) for students who prefer following along visually rather than reading, and linked them in a table near the top of the README.

## 5. Automating the review loop with GitHub Actions

Reviewing every student submission by hand doesn't scale. I built a GitHub Actions workflow ([.github/workflows](/.github/workflows)) triggered on `issues: closed` that:

- Checks whether the closed issue carries the `submission` label
- Verifies the issue was closed by the repo maintainer (not the student themselves, to prevent self-approval)
- Posts an automatic congratulations comment with a completion badge image, tagging the student
- Applies `reviewed` and `badge-assigned` labels for tracking
- **Reopens the issue and comments a warning** if anyone other than the maintainer closes it — this stops students from marking their own submissions as approved

This turned "review 50+ student submissions manually" into "close the issue, the bot does the rest."

## 6. Building the Issue Template system

To keep submissions consistent and machine-parseable (so the workflow above could reliably detect them), I added structured templates under `.github/ISSUE_TEMPLATE/`:

- `submission.yml` — a structured form (GitHub username, PR links, screenshot, reflection) instead of a free-text issue, so every submission has the same shape
- `bug_report.md`, `feature_request.md`, `question.md` — standard templates for everything else

I iterated on the submission template several times (see commit history) — originally it was a Markdown template, later converted to a YAML form for stricter structure and required fields.

## 7. Layering in deeper guides

Once the core exercise worked, I added a `guides/` folder for topics that don't belong in the main linear flow but that students ask about once they're comfortable with the basics:

- `github-pages.md` — publishing a site from a repo
- `github-profile-readme.md` — the special self-named profile README
- `gitignore.md` — what `.gitignore` does and why
- `merge-conflicts.md` — how to resolve them once students inevitably hit one
- `undoing-changes.md` — `git reset`, `revert`, `checkout` for when things go wrong

Each guide is self-contained so it can be linked to individually rather than requiring students to read the whole repo.

## 8. Adding student-opportunity documentation

Since this repo targets students specifically, I added a `student-opportunities/` section documenting how to claim GitHub Student Developer Pack perks — GitHub Foundations certification vouchers and DataCamp vouchers — including eligibility and redemption steps, since these are useful, time-limited benefits students often don't know they qualify for.

## 9. Iterating from real usage

Because this repo is actually used by students (not just a demo), most refinements came from real submissions surfacing gaps:

- Simplified the submission process after seeing confusion (`53fdb95 Remove submission review template and update README to reflect new submission process`)
- Tightened the Git configuration troubleshooting guide after repeated identical support questions
- Removed outdated sections and streamlined voucher guides as GitHub's own programs changed

## Key takeaways

- **Teach by doing, not describing.** The repo *is* the exercise — students fork, branch, and PR against a real remote, not a simulation.
- **Automate the parts that don't teach anything.** Reviewing and badge-tagging submissions is toil, not learning, so a GitHub Actions workflow handles it.
- **Push depth out of the main path.** The root README stays linear; guides, troubleshooting, and extras live in their own folders and are linked contextually.
- **Let real usage drive the roadmap.** Nearly every guide in `support md files/` exists because a real student got stuck on that exact thing.
