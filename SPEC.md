# AOS Protocol v0.1 – .well-known/agent Specification

Serve this JSON at `https://yoursite.com/.well-known/agent`.

## Schema

```json
{
  "$schema": "https://www.runaos.online/schema/agents.json",
  "site_name": "Your Site Name",
  "version": "0.1",
  "auth": {
    "type": "none | session_cookie | oauth2 | api_key"
  },
  "contact": {
    "email": "hello@yoursite.com",
    "preferred": true
  },
  "actions": [
    {
      "id": "action_name",
      "name": "Human-readable name",
      "description": "What it does",
      "method": "GET | POST",
      "url": "https://yoursite.com/api/action",
      "parameters": { /* JSON Schema */ }
    }
  ]
}