# 🎵 MoveMusic White Label

White label platform for digital music distribution. Built for record 
labels, aggregators, and distributors to manage artists, releases, 
and tracks from a fully customizable interface.

> 🧪 **Live Demo:** https://demo-test-lake.vercel.app  
> Demo credentials available on request.

## Architecture

Uses a **Backend for Frontend (BFF)** pattern with Next.js API Routes 
as the backend layer. The frontend never communicates directly with 
external services — all requests go through internal API routes that 
handle authentication, business logic, file processing, and data 
persistence before interacting with S3, MongoDB, or the MoveMusic API.

## Key Features

- Artist, album, and track management
- Chunked audio file upload with server-side assembly
- Audio format validation (WAV, 44100Hz, 16-bit, max 159MB)
- Pre-signed S3 URL generation for secure file storage
- Royalties tracking and statistics
- Multi-brand white label support
- JWT authentication with secure cookies
- Temporary session-based track storage with MongoDB

> 🔑 **Demo credentials:** user@demo.com / 123456  
> *(Read-only demo account — no real data)*

## Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | Next.js, React, Tailwind CSS |
| Backend | Next.js API Routes, TypeScript |
| Database | MongoDB (Mongoose) |
| Storage | AWS S3 |
| Auth | JWT + Secure Cookies (jose) |
| External API | MoveMusic Distribution API |
| Deployment | Vercel |

## API Highlights

- `POST /api/admin/createTrack` — chunked audio upload with 
  format validation and MongoDB persistence
- `GET /api/admin/getReleaseById/:id` — release data with 
  track verification
- JWT middleware on all protected routes
