# TrackeyAI for Cursor

A Cursor plugin that connects Cursor to the TrackeyAI MCP service and provides guidance for evidence-backed governed execution.

## What it provides

- TrackeyAI MCP server configuration at https://api.trackeyai.com/mcp
- A skill for checking the live execution contract, using authorized runs, submitting observed evidence, and reporting the authoritative outcome

Installing the plugin does not create a governed run or authorize work. Follow the user's request and the live TrackeyAI contract.

## Install

After Cursor approves and lists this plugin:

1. Open Customize in Cursor.
2. Find TrackeyAI in the Marketplace and select Install.
3. Open the plugin's MCP server settings and sign in if Cursor prompts for TrackeyAI authentication.
4. Confirm the TrackeyAI server is enabled in Customize.

For local development, place this repository under ~/.cursor/plugins/local/trackeyai, then restart Cursor or run Developer: Reload Window. Confirm the TrackeyAI MCP server and /trackeyai-governed-execution skill appear in Customize.

## Use

Ask Cursor to use TrackeyAI for a task when you want governed execution. Provide an existing run ID to continue that run, or explicitly authorize creation of a new run. The skill checks the live contract and follows TrackeyAI's current decision and evidence requirements.

If the MCP connection is unavailable or authentication fails, Cursor should report that directly. It must not claim that governance occurred.

## Security

This repository contains no credentials. Authentication is handled by Cursor and TrackeyAI's supported MCP authentication flow. Do not add access tokens, client secrets, or customer data to plugin files or issues.

## Development

- .cursor-plugin/plugin.json: Cursor plugin manifest
- mcp.json: remote TrackeyAI MCP server
- skills/trackeyai-governed-execution/SKILL.md: governed execution guidance

Cursor plugin documentation: https://cursor.com/docs/reference/plugins  
Marketplace submission: https://cursor.com/marketplace/publish
