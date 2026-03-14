# Bike Tracks API

## What this is
FastAPI backend for a bike tracking app with NFC tagging and stolen bike reporting.
This is one of 3 repos in the project (api / web / mobile).

## Stack
- **Language**: Python 3.11+
- **Framework**: FastAPI
- **Database**: PostgreSQL via SQLAlchemy (async)
- **Auth**: Firebase Auth (JWT verification)
- **Migrations**: Alembic
- **Testing**: pytest

## Project phases
- [ ] Phase 1: Backend Foundation — DB + API scaffold ← START HERE
- [ ] Phase 2: Authentication — Firebase Auth integration
- [ ] Phase 3: Bike Management — CRUD + Bike Index API
- [ ] Phase 4: Stolen Reporting — report + search endpoints
- [ ] Phase 5: (Web frontend — separate repo)
- [ ] Phase 6: (Mobile app — separate repo)

## Folder structure (target)
```
bike-tracks-api/
├── app/
│   ├── main.py          # FastAPI app entry point
│   ├── database.py      # DB connection + session
│   ├── models/          # SQLAlchemy models
│   ├── schemas/         # Pydantic schemas
│   ├── routers/         # Route handlers
│   └── dependencies.py  # Shared deps (auth, db session)
├── alembic/             # DB migrations
├── tests/
├── .env.example
├── requirements.txt
└── PROJECT_STATUS.md
```

## Working rules
- Keep it simple — don't over-engineer
- Write at least one test per new endpoint
- Use async SQLAlchemy throughout
- Never commit real credentials — use .env files
- Update PROJECT_STATUS.md after completing each phase
- Ask before making big structural decisions

## Environment variables needed
```
DATABASE_URL=postgresql+asyncpg://user:password@localhost/biketracker
FIREBASE_PROJECT_ID=your-project-id
SECRET_KEY=your-secret-key
```

## Key commands
```bash
uvicorn app.main:app --reload   # Run dev server
pytest                          # Run tests
alembic upgrade head            # Apply migrations
alembic revision --autogenerate -m "description"  # New migration
```
