# Working with EventCard submodules

The planning repository links two independent Git repositories: [backend](https://github.com/khurshedvick/event-card-backend) at `backend/` and [frontend](https://github.com/khurshedvick/event-card-frontend) at `frontend/`. `.gitmodules` stores their URLs; the planning repository stores the exact commit selected from each. Code changes belong in the child repository, while updating the selected commit belongs in planning.

## Clone everything

```sh
git clone --recurse-submodules https://github.com/khurshedvick/event-card-planning.git
```

If planning was already cloned without its submodules, run `git submodule update --init --recursive` inside it.

## Make a frontend or backend change

1. Enter `frontend/` or `backend/`. The frontend app lives on the `codex/eventcard-editor` branch; the backend is currently on `main`. A fresh submodule clone may start at a detached commit, so switch to the right branch first.
2. Make the change, run `npm run check` in `frontend/`, and test at `http://localhost:4300`.
3. Commit and push in that repository: `git push origin codex/eventcard-editor` for the frontend, `git push origin main` for the backend.
4. Return to the planning repository. Run `git add frontend` or `git add backend`, commit that pointer change, and push planning.

The child commit must be pushed before the planning pointer; otherwise other people cannot fetch the commit planning references. To inspect the recorded versions, run `git submodule status` from the planning repository. See `frontend/README.md` for the step-by-step template workflow.
