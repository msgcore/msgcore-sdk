# @msgcore/sdk

TypeScript SDK for MsgCore - Universal messaging gateway API.

> **Auto-generated from backend contracts** - Do not edit manually

## Installation

```bash
npm install @msgcore/sdk
```

## Quick Start

```typescript
import { MsgCore } from '@msgcore/sdk';

const gk = new MsgCore({
  apiUrl: 'https://api.msgcore.dev',
  apiKey: 'msc_live_your_api_key_here',
});

// Send a message
const result = await gk.messages.send({
  targets: [{ platformId: 'platform-id', type: 'user', id: '123' }],
  content: { text: 'Hello from MsgCore!' },
});
```

## Features

- ✅ **Full type safety** - TypeScript types auto-generated from backend
- ✅ **Perfect sync** - Always matches backend API contracts
- ✅ **Zero duplication** - Single source of truth from contracts
- ✅ **Error handling** - Built-in error types and authentication handling
- ✅ **Rate limiting** - Automatic rate limit detection

## API Reference

## Analysis / Entities

### List all extracted entities for a project with pagination and sorting
```typescript
// Usage example
await gk.analysisEntities.list();
```

### Get a specific extracted entity by ID
```typescript
// Usage example
await gk.analysisEntities.get('id');
```

## Analysis / Models

### List available LLM models from OpenRouter for analysis
```typescript
// Get all supported models
await gk.analysisModels.list();
```

## Analysis / Profiles

### Create a new analysis profile (versioned pipeline)
```typescript
// Create an analysis profile
await gk.analysisProfiles.create(data);
```

### List all analysis profiles for a project
```typescript
// List all profiles
await gk.analysisProfiles.list();
```

## Analysis / Runs

### Execute an analysis run with a profile
```typescript
// Run analysis on specific messages
await gk.analysisRuns.create(data);
```

### Get analysis run statistics for a project
```typescript
// Get run statistics
await gk.analysisRuns.stats();
```

## Analysis / Schemas

### Create a new entity schema for custom extraction
```typescript
// Create a sentiment analysis schema
await gk.analysisSchemas.create(data);
```

### List all entity schemas for a project
```typescript
// List all entity schemas
await gk.analysisSchemas.list();
```

## ApiKeys

### Generate a new API key
```typescript
// Create messaging API key
await gk.apikeys.create(data);
```

### List all API keys for project
```typescript
// List all API keys
await gk.apikeys.list();
```

## Auth

### Create a new user account (first user becomes admin)
```typescript
// Create first admin user
await gk.auth.signup(data);
```

### Login with email and password
```typescript
// Login with email and password
await gk.auth.login(data);
```

## Chats

### List all chats for a project with filtering and pagination
```typescript
// Usage example
await gk.chats.list(data);
```

### Get details of a specific chat
```typescript
// Usage example
await gk.chats.get('chatId');
```

## Identities

### Create a new identity with platform aliases
```typescript
// Create identity with Discord and Telegram aliases
await gk.identities.create(data);
```

### List all identities for a project
```typescript
// List all identities
await gk.identities.list();
```

## Members

### List all members of a project
```typescript
// List all project members
await gk.members.list();
```

### Add a member to a project
```typescript
// Add a member with admin role
await gk.members.add(data);
```

## Messages

### List messages for a project (sent and received)
```typescript
// Get all messages (sent + received)
await gk.messages.list(data);
```

### Get message statistics for a project
```typescript
// Get message statistics
await gk.messages.stats();
```

## Platform Logs

### List platform processing logs for a project
```typescript
// List recent platform logs
await gk.platformLogs.list();
```

### List logs for a specific platform configuration
```typescript
// List logs for specific platform
await gk.platformLogs.get('platformId');
```

## Platforms

### Configure a new platform integration
```typescript
// Add Discord bot
await gk.platforms.create(data);
```

### List configured platforms for project
```typescript
// List all platforms
await gk.platforms.list();
```

## Projects

### Create a new project
```typescript
// Create a simple project
await gk.projects.create(data);
```

### List all projects
```typescript
// List all projects
await gk.projects.list();
```

## Webhooks

### Create a new webhook for event notifications
```typescript
// Create webhook for all message events
await gk.webhooks.create(data);
```

### List all webhooks for a project
```typescript
// List all webhooks
await gk.webhooks.list();
```

## Authentication

### API Key (Recommended)

```typescript
const gk = new MsgCore({
  apiUrl: 'https://api.msgcore.dev',
  apiKey: 'msc_live_your_api_key_here',
  defaultProject: 'my-project', // optional
});
```

### JWT Token

```typescript
const gk = new MsgCore({
  apiUrl: 'https://api.msgcore.dev',
  jwtToken: 'your-jwt-token',
});
```

## Error Handling

```typescript
import { MsgCoreError, AuthenticationError, RateLimitError } from '@msgcore/sdk';

try {
  await gk.messages.send({ ... });
} catch (error) {
  if (error instanceof AuthenticationError) {
    console.error('Invalid credentials');
  } else if (error instanceof RateLimitError) {
    console.error('Rate limit exceeded');
  } else if (error instanceof MsgCoreError) {
    console.error(`API error: ${error.message}`);
  }
}
```

## Links

- [Documentation](https://docs.msgcore.dev)
- [GitHub](https://github.com/msgcore/msgcore-sdk)
- [npm](https://www.npmjs.com/package/@msgcore/sdk)
- [Discord Community](https://discord.gg/bQPsvycW)

## License

MIT
