# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- `npm run dev` - Start development server with Turbopack for fast builds
- `npm run build` - Build the application for production
- `npm start` - Start the production server
- `npm run lint` - Run ESLint to check code quality

## Project Architecture

This is a Next.js 15 application implementing a LiveKit video conferencing room management system.

### Key Components

- **App Router Structure**: Uses Next.js App Router with TypeScript
- **Main Room Interface** (`app/page.tsx`): Primary video conferencing interface with room management
- **Room Page** (`app/room/page.tsx`): Currently a single-line file, appears to be minimal
- **API Routes** (`app/api/token/route.ts`): Handles LiveKit token generation, room listing, and deletion

### LiveKit Integration

The application uses LiveKit for real-time video conferencing:

- **Client Libraries**: `@livekit/components-react`, `livekit-client`
- **Server SDK**: `livekit-server-sdk` for room management
- **Required Environment Variables**:
  - `LIVEKIT_API_KEY`
  - `LIVEKIT_API_SECRET` 
  - `LIVEKIT_URL`
  - `NEXT_PUBLIC_LIVEKIT_URL`

### API Endpoints

- `GET /api/token?room={name}&username={user}` - Generate access token for room
- `POST /api/token` - List all active rooms
- `DELETE /api/token?room={name}` - Delete room and disconnect participants

### Technology Stack

- **Framework**: Next.js 15 with App Router
- **Runtime**: React 19
- **Styling**: Tailwind CSS 4, inline styles for LiveKit components
- **TypeScript**: Full TypeScript configuration
- **Fonts**: Geist Sans and Geist Mono from Google Fonts

### Key Features

- Real-time video conferencing with adaptive streaming
- Room creation and management interface
- Participant management and room cleanup
- Session management with localStorage integration
- Room deletion with participant disconnection

### Development Notes

- Uses Turbopack for fast development builds
- ESLint configured with Next.js recommended settings
- Strict TypeScript configuration enabled
- No test framework currently configured