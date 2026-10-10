# [Project Title]

Individual project for the Advanced Programming Methods course, academic year 2026-2027.

## Description
The project analyzes logs.

## Rules

- Lines that do not match the format are ignored and counted in `ignored`, without causing an error.
- An unknown level makes the line invalid.
- An alert is reported as `{"start", "end", "error_count"}`, where `start` is the time of the first error in the window.
- Alerts do not overlap: after a window has generated an alert, the analysis continues from the first error after the end of that window.
- The window is inclusive at both ends: an error occurring exactly T minutes after the window's first error is counted in the same window.

**Parameters:** K = 5 errors within a window of T = 10 minutes

## Technologies

TypeScript on Node 22, with Express

## Running

```
docker build -t map-proiect .
docker run -d -p 8080:8080 map-proiect
```

The application listens on port 8080. Verify with:

```
curl http://localhost:8080/health
curl http://localhost:8080/version
```

## Testing

```
npm ci
npm test
```

## Implemented Routes

| Route | Method | Description |
|---|---|---|
| `/health` | GET | Service status |
| `/version` | GET | Version and the commit the image was built from |
| `/` | GET | Landing page |
| `/reset` | POST | Clears the in-memory data |
| [topic route] | [method] | [description] |

## Implementation Decisions

[Two or three technical decisions you made and the reasoning behind each.]