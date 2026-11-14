# Interview transcript

### You

I want to build an app that will let me generate documentation automatically for my github repos

### Keel

Good start. Two questions:

1. What form should it take? I'd suggest a web app where you connect GitHub, pick a repo, and get generated docs. A CLI or GitHub Action are alternatives.
2. What should it produce: a README, API reference, a markdown docs folder committed back to the repo, or something else?

### You

1. web app
2. all of these

### Keel

Next:

1. Who is this for: just you, or other developers too? That decides auth. I'd suggest "Sign in with GitHub" for everyone.
2. After generating, should the app commit the docs back to the repo (e.g. via a pull request), or only let you view and download them? I'd suggest a pull request as the default.

### You

1. other developers too
2. yes pr

### Keel

Three more things:

1. Name: any preference? Otherwise I'll use "RepoDocs".
2. Storage: should the app save users and their generation history (repo, date, output, PR link)? I'd suggest yes, with entities User, Repository, and Generation.
3. Where will it be deployed (e.g. Vercel, Fly.io, AWS)? And how should docs be generated: with an LLM reading the code? That affects constraints.

### You

1. come up with a better unique name
2. yes
3. you make the decision. and docs should be generated with an llm reading code

### Keel

I've filled in the rest:

- **Name:** Docsmith.
- **Deployment:** Vercel with managed Postgres.
- **Data model:** User, Repository and Generation.
- **Integrations:** GitHub and an LLM provider.
- **Out of scope:** GitLab and Bitbucket, auto-regeneration on every push, and team management.

Is this right? If you confirm, I'll finalize it.

### You

confirm
