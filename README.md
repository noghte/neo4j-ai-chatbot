<a href="https://sveltekit-ai-chatbot.vercel.app/">
<h1 align="center">SvelteKit AI Chatbot</h1>
</a>

<p align="center">
  An open-source AI chatbot app template built with SvelteKit, the Vercel AI SDK, OpenAI, and Vercel KV.
</p>

<p align="center">
  <a href="#features"><strong>Features</strong></a> ·
  <a href="#model-providers"><strong>Model Providers</strong></a> ·
  <a href="#deploy-your-own"><strong>Deploy Your Own</strong></a> ·
  <a href="#running-locally"><strong>Running locally</strong></a> ·
  <a href="#authors"><strong>Authors</strong></a>
</p>
<br/>

This is an **unofficial** SvelteKit port of [vercel-labs/ai-chatbot](https://github.com/vercel-labs/ai-chatbot).

## Features

- [SvelteKit](https://kit.svelte.dev)
- [Vercel AI SDK](https://sdk.vercel.ai/docs) for streaming chat UI
- Support for OpenAI (default), Anthropic, HuggingFace, or custom AI chat models and/or LangChain
- Edge runtime-ready
- [shadcn/ui](https://ui.shadcn.com) and [shadcn-svelte](https://github.com/huntabyte/shadcn-svelte)
  - Styling with [Tailwind CSS](https://tailwindcss.com)
  - [Radix Svelte](https://www.radix-svelte.com) and [Svelte Headless UI](https://svelte-headlessui.goss.io) for headless component primitives
  - Icons from [Phosphor Icons](https://phosphoricons.com)
- Chat History, rate limiting, and session storage with [Vercel KV](https://vercel.com/storage/kv) (🚧 Under construction)
- [Auth.js](https://authjs.dev) for authentication

## Model Providers

This template ships with OpenAI `gpt-3.5-turbo` as the default. However, thanks to the [Vercel AI SDK](https://sdk.vercel.ai/docs), you can switch LLM providers to [Anthropic](https://anthropic.com), [HuggingFace](https://huggingface.co), or using [LangChain](https://js.langchain.com) with just a few lines of code.



## Creating a KV Database Instance

Follow the steps outlined in the [quick start guide](https://vercel.com/docs/storage/vercel-kv/quickstart#create-a-kv-database) provided by Vercel. This guide will assist you in creating and configuring your KV database instance on Vercel, enabling your application to interact with it.

Remember to update your environment variables (`KV_URL`, `KV_REST_API_URL`, `KV_REST_API_TOKEN`, `KV_REST_API_READ_ONLY_TOKEN`) in the `.env` file with the appropriate credentials provided during the KV database setup.

## Running locally

You will need to use the environment variables [defined in `.env.example`](.env.example) to run Next.js AI Chatbot. It's recommended you use [Vercel Environment Variables](https://vercel.com/docs/concepts/projects/environment-variables) for this, but a `.env` file is all that is necessary.

> Note: You should not commit your `.env` file or it will expose secrets that will allow others to control access to your various OpenAI and authentication provider accounts.

1. Install Vercel CLI: `npm i -g vercel`
2. Link local instance with Vercel and GitHub accounts (creates `.vercel` directory): `vercel link`
3. Download your environment variables: `vercel env pull`

```bash
npm install

npm run dev
# or start the server and open the app in a new browser tab
npm run dev -- --open
```

Your app template should now be running on [localhost:5173](http://localhost:5566/).

## Authors

This template is based on [jianyuan/sveltekit-ai-chatbot/](https://github.com/jianyuan/sveltekit-ai-chatbot/) and [Next.js version](https://github.com/vercel-labs/ai-chatbot).
