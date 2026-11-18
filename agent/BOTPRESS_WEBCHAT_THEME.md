# Botpress Webchat theme — burgundy and red

> **Not applied yet.** This file documents the recommended settings; it does not change the live Botpress bot. Do not publish Botpress configuration until the project owner approves and checks the preview.

## Recommended palette

Use the same palette as the website:

| Use | Color |
|---|---|
| Main brand / primary color | `#641B2D` |
| Red accent / focus state | `#B52E43` |
| Dark wine accent | `#7E2035` |
| Soft rose surface | `#FFF7F6` |
| White surface | `#FFFDFC` |
| Main text | `#291A1E` |
| Muted text | `#6C5960` |
| Borders | `#EAD6D8` |

The recommended Botpress appearance is **Light** mode with the primary color set to **`#641B2D`**. This matches the site's burgundy identity while keeping the chat readable against its warm white and pale rose backgrounds.

## Apply in Botpress

1. Open the Botpress workspace and select the Health Information Checker bot.
2. Go to **Webchat → Bot Appearance**.
3. Set **Primary colour** to `#641B2D`; keep **Theme mode** on **Light**.
4. Review the preview. If the primary setting leaves some components unchanged, use the optional CSS below in the **Styles** section.
5. Do not select **Publish Configuration** until Hamza approves the preview. Publishing changes the Botpress webchat configuration; this repository change alone does not.

### Optional CSS for Botpress “Styles”

These selectors are from Botpress's documented Webchat CSS class list. Paste this only into the bot's Botpress **Styles** field—not into the website's CSS:

```css
.bpHeaderContainer {
  background-color: #641B2D !important;
  color: #FFFFFF !important;
}

.bpHeaderContentTitle {
  color: #FFFFFF !important;
}

.bpHeaderContentDescription {
  color: rgba(255, 255, 255, 0.82) !important;
}

.bpComposerSendButton {
  background-color: #641B2D !important;
  border-color: #641B2D !important;
  color: #FFFFFF !important;
}

.bpComposerInput:focus {
  border-color: #B52E43 !important;
  box-shadow: 0 0 0 2px rgba(181, 46, 67, 0.15) !important;
}

.bpMessageBlocksBubble {
  background-color: #FFF7F6 !important;
  border: 1px solid #EAD6D8 !important;
  color: #291A1E !important;
}

.bpMessageBlocksTextLink {
  color: #7E2035 !important;
}
```

Check the preview for message contrast and button text before publishing. If a selector has no effect in the current Webchat version, remove that rule rather than adding broad global overrides.

## Important embed limitation

The current `index.html` embeds Botpress at `https://vdk-viber-runtime-prod.bot.botpress.host/edge/?botId=…` inside a cross-origin `<iframe>`. CSS on the project website can style the iframe's border and container, but it cannot reach inside and recolor Botpress's header, message bubbles, or buttons. Do not add guessed color query parameters or parent-page CSS selectors and claim that they changed the embedded chat.

Botpress's current documentation directs bot owners to configure appearance in the Dashboard, then publish the Webchat configuration. Its current embed guide obtains the deploy code from **Webchat → Deploy Settings**. The repository does not contain the bot's dashboard configuration or that dashboard-generated embed code, so this branch intentionally does not replace the working iframe with guessed IDs or scripts. If the dashboard preview does not affect the existing iframe, the owner should copy the exact current embed code from that bot's Deploy Settings and test it on a preview branch before replacing the existing embed.

## Official Botpress documentation

- [Configure Webchat appearance and styles](https://botpress.com/docs/webchat/get-started/configure-your-webchat/)
- [Embed Webchat](https://botpress.com/docs/webchat/get-started/embedding-webchat/)
- [Update Webchat configuration](https://botpress.com/docs/webchat/interact/update-config/)
