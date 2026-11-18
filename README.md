# EventCard planning

This repository holds agent-facing product planning for EventCard. Start with [docs/README.md](docs/README.md) for the current decisions, open questions, and reference notes.

The [backend](backend) and [frontend](frontend) directories are separate Git repositories linked as submodules. See [docs/submodules.md](docs/submodules.md) to clone and work with them. The frontend submodule records rollback commit `390ef38` (the `8107cf3` content); the editor verified as currently deployed at `app.eventcard.cc` is `42dea82`, which has not been redeployed. The backend is still a placeholder. A mobile app or other service can be added later if needed.

For local development, run `npm run dev` inside `frontend/` and open `http://localhost:4300`. See `frontend/README.md` for the template workflow.
