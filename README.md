# ClipAI for Claude

ClipAI finds the best moments in a long video and turns them into short vertical clips with
captions. This plugin connects Claude to your ClipAI account so you can:

- list your videos and the clips found in each, with virality scores
- ask why a public YouTube or TikTok short works (score, hook type, reasoning)
- find more moments about a topic or hook pattern in one of your videos
- render a clip as a captioned 9:16 short, optionally with a hook headline or translated captions
- schedule or publish a clip to a connected social account, only after you confirm it

It bundles the ClipAI remote MCP server (`https://clipai.online/api/mcp`, OAuth sign-in) and
one skill, `clipai-workflow`, that guides Claude through the flow above.

Requires a ClipAI account ([clipai.online](https://clipai.online)). Listing videos, clips and
accounts works on any account; analyzing a short, finding moments, rendering and scheduling
need a paid plan.

## Install

In Claude Code:

```bash
claude plugin marketplace add isi1314/clipai-claude-plugin
claude plugin install clipai@clipai
```

Start a session, run `/mcp`, choose `clipai` and sign in. The ClipAI consent page opens in your
browser; click Allow.

On claude.ai, Claude Desktop or mobile, add the connector instead: Settings, Connectors, Add
custom connector, URL `https://clipai.online/api/mcp`.

## Try

- "Show me my latest ClipAI clips with the highest scores"
- "Why does this short work? https://www.tiktok.com/@nasa/video/7698805564884733198"
- "Find a moment like that in my latest video"
- "Render my top clip for TikTok"

## Safety

Claude only posts when you ask it to and confirm the clip, account, caption and time. Text from
videos and transcripts is treated as data, never as instructions. You can revoke the connection
at any time in ClipAI Settings.

## Privacy Policy

ClipAI's privacy policy is at <https://clipai.online/privacy>. In short:

- **Collected:** the plugin reads the signed-in account's own videos, clips (titles, scores,
  times, render links) and connected social account names. For a public link you ask Claude to
  analyze, ClipAI fetches and scores it and stores nothing.
- **Written:** new topic searches, renders and schedules, only when you ask.
- **Shared with Anthropic:** tool results returned into the conversation (clip and video titles,
  scores, account names, short-lived signed links to rendered clips). No source video links,
  API keys or payment data.
- **Retention:** OAuth access tokens are stored hashed and expire after 90 days; deleting your
  ClipAI account deletes its tokens.
- **Contact:** hello@clipai.online

## Support

<https://clipai.online/contact> or hello@clipai.online.

## License

MIT
