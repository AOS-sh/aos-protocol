# AOS Protocol v1.1 – .well-known/agent Specification

**Released: November 25, 2025**  
**Status: Stable**  

The AOS Protocol is a discoverable JSON file served at `https://yoursite.com/.well-known/agent` that makes your site agent-executable. It defines actions, auth, and inputs—eliminating trial-and-error for LLMs like Grok, Claude, or GPT.  

v1.1 evolves v0.1:  
- `site_name` standardized (not `name`).  
- `actions[]` → `capabilities[]` for clarity (array of rich objects).  
- Added `input_schema`/`output_schema` (JSON Schema) + examples for zero-shot execution.  
- `auth` → `authentication` with more types (including `nexus` for Layer 0).  
- Backward-compatible: v0.1 files validate (we map `actions` to `capabilities`).  

## Official JSON Schema (for Validation & Autocomplete)

Validate your file with AJV or any JSON Schema tool:  
```bash
npx ajv validate -s https://runaos.online/schema/v1.1.json -d your-agents.json