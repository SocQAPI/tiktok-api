<!-- Generated from the SocQ API catalog and docs. Do not edit by hand. -->
# TikTok API

[![SocQ TikTok API](https://img.shields.io/badge/API-SocQ%20TikTok%20API-F64C31)](https://socq.ai/apis/tiktok?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)
[![API documentation](https://img.shields.io/badge/Docs-docs.socq.ai-111827)](https://docs.socq.ai/api-manual/tiktok/overview)
[![License: MIT](https://img.shields.io/badge/License-MIT-2563EB)](LICENSE)
[![Check examples](https://github.com/SocQAPI/tiktok-api/actions/workflows/check.yml/badge.svg)](https://github.com/SocQAPI/tiktok-api/actions/workflows/check.yml)

32 endpoints for public TikTok data through one SocQ API key, with runnable cURL, Node.js and Python examples and a valid request body for every endpoint.

[Browse TikTok APIs](https://socq.ai/apis/tiktok?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api) · [Get an API key](https://socq.ai/dashboard/api-key?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api) · [Documentation](https://docs.socq.ai/api-manual/tiktok/overview) · [All SocQ examples](https://github.com/SocQAPI/socq-examples)

> **Need a ready-made app?** [Open Social Listening](https://github.com/SocQAPI/open-social-listening) is a free, open-source social listening tool you host yourself, built on SocQ search endpoints. It tracks brand, competitor and topic mentions on Reddit, X, YouTube, TikTok, news and the web.

## Endpoints

Prices are in SocQ credits; 1 credit = $0.005.

| Endpoint | publicId | What it returns | Price | Launched |
| --- | --- | --- | --- | --- |
| [TikTok Profiles API](#tiktok-profiles-api) | `tiktok/profiles` | Retrieve normalized public TikTok profile identity, biography, account flags, and visible follower, following, video, and like counts by username. | 0.6 credits ($0.003) per result | 2026-07-16 |
| [TikTok Hashtags API](#tiktok-hashtags-api) | `tiktok/hashtags` | Collect normalized public TikTok videos for one or more hashtags, with creator, caption, engagement, media, sound, and matched-hashtag context. | 0.7 credits ($0.0035) per result | 2026-07-16 |
| [TikTok Comments API](#tiktok-comments-api) | `tiktok/comments` | Collect normalized publicly visible top-level TikTok comments from direct video URLs, including text, author context, likes, reply counts, mentions, and creator interaction flags. | 0.25 credits ($0.00125) per result | 2026-07-16 |
| [TikTok Videos API](#tiktok-videos-api) | `tiktok/videos` | Retrieve normalized public TikTok video metadata from direct video URLs, including creator, caption, engagement, cover references, hashtags, mentions, and sound details. | 0.7 credits ($0.0035) per result | 2026-07-16 |
| [TikTok Search API](#tiktok-search-api) | `tiktok/search` | Search public TikTok videos by query and return normalized video records with supported relevance, date, likes, and publication-window filters. | 0.7 credits ($0.0035) per result | 2026-07-16 |
| [TikTok Comment Replies API](#tiktok-comment-replies-api) | `tiktok/comment-replies` | Collect public TikTok replies for one comment using a video URL and comment ID, returning text, authors, timestamps, engagement, and parent context as normalized records. | 0.5 credits ($0.0025) per result | 2026-07-25 |
| [TikTok Followers List API](#tiktok-followers-list-api) | `tiktok/followers-list` | Collect normalized public profile records visible in the follower lists of one or more TikTok usernames, with source context and available public metrics. | 0.5 credits ($0.0025) per result | 2026-07-25 |
| [TikTok Following List API](#tiktok-following-list-api) | `tiktok/following-list` | Collect normalized public profiles followed by one or more TikTok usernames, including identity, biography, avatar, visible profile metrics, and source username. | 0.5 credits ($0.0025) per result | 2026-07-25 |
| [TikTok User Videos API](#tiktok-user-videos-api) | `tiktok/user-videos` | Collect public TikTok videos from one or more usernames, returning captions, creators, media, timestamps, and visible engagement as normalized account-linked records. | 0.5 credits ($0.0025) per result | 2026-07-25 |
| [TikTok Live Room Info API](#tiktok-live-room-info-api) | `tiktok/live-room-info` | Retrieve a point-in-time public TikTok live room snapshot from its room and owner IDs, including title, status, owner identity, cover image, viewer count, and like count. | 0.5 credits ($0.0025) per result | 2026-07-27 |
| [TikTok Trending Feed API](#tiktok-trending-feed-api) | `tiktok/trending-feed` | Collect the current public TikTok video feed for a region code, returning video IDs, captions, creators, cover images, timestamps, and visible engagement. | 0.7 credits ($0.0035) per result | 2026-07-27 |
| [TikTok Video Transcript API](#tiktok-video-transcript-api) | `tiktok/video-transcript` | Extract transcripts from public TikTok video URLs with an optional language, returning text, language, format, source links, and collection time as normalized records. | 0.5 credits ($0.0025) per result | 2026-07-27 |
| [TikTok Search Users API](#tiktok-search-users-api) | `tiktok/search-users` | Search public TikTok creators and accounts by keyword, returning normalized identity, biography, account flags, and visible follower, following, and video counts. | 0.6 credits ($0.003) per result | 2026-09-11 |
| [TikTok Song API](#tiktok-song-api) | `tiktok/song` | Collect detailed public TikTok sound and music metadata by clip ID or sound URL, returning author, album, duration, audio links, and video usage count. | 0.5 credits ($0.0025) per result | 2026-09-11 |
| [TikTok Song Videos API](#tiktok-song-videos-api) | `tiktok/song-videos` | Collect public TikTok videos that use a specific sound, returning normalized video metadata, creator details, captions, media links, and engagement counters. | 0.5 credits ($0.0025) per result | 2026-09-11 |
| [TikTok Popular Songs API](#tiktok-popular-songs-api) | `tiktok/popular-songs` | Get the TikTok Top 50 or Viral 50 songs chart, with track names, artists, sound IDs and available video counts to help you build a music list for review. | 0.5 credits ($0.0025) per result | 2026-10-16 |
| [TikTok Top Search API](#tiktok-top-search-api) | `tiktok/top-search` | Search TikTok videos and photo carousels by keyword, with captions, creator details, media links and engagement counts returned together in one JSON list. | 0.7 credits ($0.0035) per result | 2026-10-16 |
| [TikTok User Live API](#tiktok-user-live-api) | `tiktok/user-live` | Check whether public TikTok accounts are live by username, returning live or offline status and available room details for multiple accounts in one request. | 0.5 credits ($0.0025) per result | 2026-10-16 |
| [TikTok Audience Demographics API](#tiktok-audience-demographics-api) | `tiktok/user-audience` | Retrieve the country breakdown of a public TikTok account's followers by username, returning each country's name, ISO code, audience share, and sampled follower count. | 20 credits ($0.10) per call | 2026-11-17 |
| [TikTok Similar Accounts API](#tiktok-similar-accounts-api) | `tiktok/similar-users` | Find public TikTok accounts that TikTok recommends as similar to a username, returning handles, display names, bios, follower and video counts, and verification status. | 0.5 credits ($0.0025) per result | 2026-11-17 |
| [TikTok Reposts API](#tiktok-reposts-api) | `tiktok/user-reposts` | Collect the videos a public TikTok account has reposted from its username, returning each video's caption, original author, views, likes, hashtags, and video file. | 0.5 credits ($0.0025) per result | 2026-11-17 |
| [TikTok Playlists API](#tiktok-playlists-api) | `tiktok/user-playlists` | List the public playlists of a TikTok account by username, returning each playlist's ID, name, link, cover image, video count, and owner details. | 0.5 credits ($0.0025) per result | 2026-11-17 |
| [TikTok Hashtag Views API](#tiktok-hashtag-views-api) | `tiktok/hashtag-detail` | Look up as many as 20 TikTok hashtags in one request, returning each hashtag's ID, link, total video count, and total views for side-by-side comparison. | 0.5 credits ($0.0025) per result | 2026-11-17 |
| [TikTok Sound Search API](#tiktok-sound-search-api) | `tiktok/search-music` | Search TikTok's sound library by keyword, returning sound IDs, titles, artists, cover art, durations, playable previews, and how many videos use each sound. | 0.6 credits ($0.003) per result | 2026-11-17 |
| [TikTok Live Search API](#tiktok-live-search-api) | `tiktok/search-live` | Search TikTok LIVE streams broadcasting now by keyword, returning room IDs, stream titles, hosts, current viewers, likes, and start times, ready for product lookups. | 0.6 credits ($0.003) per result | 2026-11-17 |
| [TikTok Photo Search API](#tiktok-photo-search-api) | `tiktok/search-photos` | Search TikTok photo carousel posts by keyword, returning every slideshow image along with captions, authors, hashtags, views, likes, comments, and shares. | 0.6 credits ($0.003) per result | 2026-11-17 |
| [TikTok Trending Searches API](#tiktok-trending-searches-api) | `tiktok/trending-keywords` | Collect today's trending searches on TikTok in a single call, returning about 100 search phrases in TikTok's ranked order with a ready-made search link for each. | 0.5 credits ($0.0025) per call | 2026-11-17 |
| [TikTok Creator Search Insights API](#tiktok-creator-search-insights-api) | `tiktok/search-insights` | Retrieve popular TikTok searches from Creator Search Insights, returning each search's popularity score, seven-point trend, related video count, category, and labels. | 1 credit ($0.005) per call | 2026-11-17 |
| [TikTok Live Ranking API](#tiktok-live-ranking-api) | `tiktok/live-ranking` | Collect TikTok's LIVE daily creator ranking in one call, returning up to 99 hosts with their rank, gift-based score, username, display name, and follower count. | 0.5 credits ($0.0025) per call | 2026-11-17 |
| [TikTok Live Shopping API](#tiktok-live-shopping-api) | `tiktok/live-products` | Collect the products in a TikTok LIVE stream's shopping bag from its room and host IDs, returning titles, current prices, units sold, seller IDs, and product images. | 0.1 credits ($0.0005) per result | 2026-11-17 |
| [TikTok Fake Views Checker API](#tiktok-fake-views-checker-api) | `tiktok/fake-views` | Check a public TikTok video URL for fake views, returning a fake-view score, estimated fake views and their share, the traffic tier reached, and the main reason found. | 5 credits ($0.025) per call | 2026-11-17 |
| [TikTok Comment Keywords API](#tiktok-comment-keywords-api) | `tiktok/comment-keywords` | Extract the keywords that come up most in a public TikTok video's comments from its URL, returning ranked keywords, each with the comments and likes behind it. | 1 credit ($0.005) per call | 2026-11-17 |

## Quick start

1. Create an API key at [socq.ai/dashboard/api-key](https://socq.ai/dashboard/api-key?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api).
2. Export it. The examples read only `SOCQ_API_KEY`.

```bash
git clone https://github.com/SocQAPI/tiktok-api.git
cd tiktok-api
export SOCQ_API_KEY="your-api-key"
```

3. Run any endpoint by its publicId. Without a second argument the script sends `payloads/<slug>.json`; pass a JSON file or an inline JSON object to change the input.

```bash
# Node.js 20+
node examples/node/socq.mjs tiktok/profiles

# Python 3.8+ (standard library only)
python3 examples/python/socq.py tiktok/profiles payloads/profiles.json

# cURL + jq
bash examples/curl/socq.sh tiktok/profiles '{"usernames":["example","@creator"]}'
```

Each script submits the task, polls it until it succeeds or fails, follows every result page, and writes the records to `output/<slug>-<task_id>.json`. Run `npm run check` to validate the payloads and scripts offline.

Never expose `SOCQ_API_KEY` in browser code, mobile apps, public repositories, screenshots, fixtures or logs.

## How the API works

Base URL `https://api.socq.ai`. Every request sends the API key as a bearer token:

```http
Authorization: Bearer <SOCQ_API_KEY>
Content-Type: application/json
```

All endpoints are asynchronous:

```text
POST /v1/<publicId>  ->  data.task_id  ->  GET /v1/tasks/{task_id}  ->  queued | running | succeeded | failed
```

1. **Submit** the JSON body to `POST https://api.socq.ai/v1/<publicId>`. The response returns `data.task_id` immediately; it means the task was created, not that data is ready.
2. **Poll** `GET https://api.socq.ai/v1/tasks/{task_id}` until `data.status` is `succeeded` or `failed` (a failed task carries `data.error_message`).
3. **Read results.** A succeeded task returns normalized records in `data.results.items`. Use `limit` (default 50, max 500) and pass `data.results.next_cursor` as `cursor` while `data.results.has_more` is true. `fields` selects up to 50 comma-separated fields or dot paths.
4. **Raw files (optional).** `GET https://api.socq.ai/v1/tasks/{task_id}/files` lists raw JSONL exports.

```bash
curl "https://api.socq.ai/v1/tasks/$TASK_ID?limit=100" \
  -H "Authorization: Bearer $SOCQ_API_KEY"

curl "https://api.socq.ai/v1/tasks/$TASK_ID?limit=100&cursor=$NEXT_CURSOR" \
  -H "Authorization: Bearer $SOCQ_API_KEY"
```

`callback_url` (where an endpoint accepts it) makes SocQ POST to your URL when the task reaches a terminal state; keep polling as a fallback.

**Billing.** A submit may reserve credits from `results_limit` or the number of submitted inputs; when the task finishes SocQ settles the charge from the actual result count and returns unused reserved credits. `402` means insufficient credits.

**Errors.** `400` invalid body or unsupported field, `401` missing or invalid key, `402` insufficient credits, `403` IP allowlist or task owned by another account, `404` endpoint or task not found, `422` input validation failed, `429` rate or credit-window limit (respect `Retry-After`), `500` submission failed. A client-side timeout does not cancel a task: resume polling the same `task_id` instead of submitting again.

Reference: [Authentication](https://docs.socq.ai/api-manual/agent-api/authentication) · [Task status and results](https://docs.socq.ai/api-manual/agent-api/status) · [Task files](https://docs.socq.ai/api-manual/agent-api/files) · [Callbacks](https://docs.socq.ai/api-manual/agent-api/callbacks) · [Errors](https://docs.socq.ai/api-manual/agent-api/errors)

## Endpoint reference

### TikTok Profiles API

Retrieve normalized public TikTok profile identity, biography, account flags, and visible follower, following, video, and like counts by username.

- **Request:** `POST https://api.socq.ai/v1/tiktok/profiles`
- **publicId:** `tiktok/profiles`
- **Price:** 0.6 credits ($0.003) per result
- **Launched:** 2026-07-16
- **Example body:** [`payloads/profiles.json`](payloads/profiles.json)

Collect one normalized profile record for each public username. A leading `@` is optional.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `usernames` | array of string | Yes | Public account usernames. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/profiles" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "usernames": [
    "example",
    "@creator"
  ]
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/profiles](https://docs.socq.ai/api-manual/tiktok/profiles) · Landing page: [socq.ai/apis/tiktok/profiles](https://socq.ai/apis/tiktok/profiles?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Hashtags API

Collect normalized public TikTok videos for one or more hashtags, with creator, caption, engagement, media, sound, and matched-hashtag context.

- **Request:** `POST https://api.socq.ai/v1/tiktok/hashtags`
- **publicId:** `tiktok/hashtags`
- **Price:** 0.7 credits ($0.0035) per result
- **Launched:** 2026-07-16
- **Example body:** [`payloads/hashtags.json`](payloads/hashtags.json)

Collect public videos for one or more hashtags. A leading `#` is optional.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `hashtags` | array of string | Yes | Hashtags with or without the # prefix. (items at least 1) |
| `results_limit` | integer | No | (value 1 to 2000) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/hashtags" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "hashtags": [
    "tutorial",
    "#python"
  ],
  "results_limit": 50
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/hashtags](https://docs.socq.ai/api-manual/tiktok/hashtags) · Landing page: [socq.ai/apis/tiktok/hashtags](https://socq.ai/apis/tiktok/hashtags?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Comments API

Collect normalized publicly visible top-level TikTok comments from direct video URLs, including text, author context, likes, reply counts, mentions, and creator interaction flags.

- **Request:** `POST https://api.socq.ai/v1/tiktok/comments`
- **publicId:** `tiktok/comments`
- **Price:** 0.25 credits ($0.00125) per result
- **Launched:** 2026-07-16
- **Example body:** [`payloads/comments.json`](payloads/comments.json)

Collect top-level comments from one or more public video URLs.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `results_limit` | integer | No | (value 1 to 2000) |
| `urls` | array of string | Yes | Public profile or content URLs. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/comments" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "urls": [
    "https://www.tiktok.com/@example/video/7234567890123456789"
  ],
  "results_limit": 100
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/comments](https://docs.socq.ai/api-manual/tiktok/comments) · Landing page: [socq.ai/apis/tiktok/comments](https://socq.ai/apis/tiktok/comments?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Videos API

Retrieve normalized public TikTok video metadata from direct video URLs, including creator, caption, engagement, cover references, hashtags, mentions, and sound details.

- **Request:** `POST https://api.socq.ai/v1/tiktok/videos`
- **publicId:** `tiktok/videos`
- **Price:** 0.7 credits ($0.0035) per result
- **Launched:** 2026-07-16
- **Example body:** [`payloads/videos.json`](payloads/videos.json)

Collect one normalized video record for each public video URL.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `urls` | array of string | Yes | Public profile or content URLs. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/videos" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "urls": [
    "https://www.tiktok.com/@example/video/7234567890123456789"
  ]
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/videos](https://docs.socq.ai/api-manual/tiktok/videos) · Landing page: [socq.ai/apis/tiktok/videos](https://socq.ai/apis/tiktok/videos?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Search API

Search public TikTok videos by query and return normalized video records with supported relevance, date, likes, and publication-window filters.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search`
- **publicId:** `tiktok/search`
- **Price:** 0.7 credits ($0.0035) per result
- **Launched:** 2026-07-16
- **Example body:** [`payloads/search.json`](payloads/search.json)

Search public videos using stable filters.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `published_within` | string | No | - |
| `query` | string | Yes | Search query. |
| `results_limit` | integer | No | (value 1 to 2000) |
| `sort_by` | string | No | - |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "python tutorial",
  "results_limit": 50,
  "sort_by": "relevance",
  "published_within": "month"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search](https://docs.socq.ai/api-manual/tiktok/search) · Landing page: [socq.ai/apis/tiktok/search](https://socq.ai/apis/tiktok/search?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Comment Replies API

Collect public TikTok replies for one comment using a video URL and comment ID, returning text, authors, timestamps, engagement, and parent context as normalized records.

- **Request:** `POST https://api.socq.ai/v1/tiktok/comment-replies`
- **publicId:** `tiktok/comment-replies`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-25
- **Example body:** [`payloads/comment-replies.json`](payloads/comment-replies.json)

Collect public replies for a TikTok comment. Results are normalized and billed by the actual saved record count.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `comment_id` | string | Yes | A public comment identifier. |
| `results_limit` | integer | No | (value 20 to 2000; default `100`) |
| `url` | string | Yes | A public content or product URL. |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/comment-replies" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "url": "https://www.tiktok.com/@scout2015/video/6718335390845095173",
  "comment_id": "6718335906996502534",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/comment-replies](https://docs.socq.ai/api-manual/tiktok/comment-replies) · Landing page: [socq.ai/apis/tiktok/comment-replies](https://socq.ai/apis/tiktok/comment-replies?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Followers List API

Collect normalized public profile records visible in the follower lists of one or more TikTok usernames, with source context and available public metrics.

- **Request:** `POST https://api.socq.ai/v1/tiktok/followers-list`
- **publicId:** `tiktok/followers-list`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-25
- **Example body:** [`payloads/followers-list.json`](payloads/followers-list.json)

Collect public TikTok follower profiles. Results are normalized and billed by the actual saved record count.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 20 to 2000; default `100`) |
| `usernames` | array of string | Yes | Public account usernames. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/followers-list" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "usernames": [
    "@tiktok"
  ],
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/followers-list](https://docs.socq.ai/api-manual/tiktok/followers-list) · Landing page: [socq.ai/apis/tiktok/followers-list](https://socq.ai/apis/tiktok/followers-list?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Following List API

Collect normalized public profiles followed by one or more TikTok usernames, including identity, biography, avatar, visible profile metrics, and source username.

- **Request:** `POST https://api.socq.ai/v1/tiktok/following-list`
- **publicId:** `tiktok/following-list`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-25
- **Example body:** [`payloads/following-list.json`](payloads/following-list.json)

Collect public TikTok following profiles. Results are normalized and billed by the actual saved record count.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 20 to 2000; default `100`) |
| `usernames` | array of string | Yes | Public account usernames. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/following-list" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "usernames": [
    "@tiktok"
  ],
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/following-list](https://docs.socq.ai/api-manual/tiktok/following-list) · Landing page: [socq.ai/apis/tiktok/following-list](https://socq.ai/apis/tiktok/following-list?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok User Videos API

Collect public TikTok videos from one or more usernames, returning captions, creators, media, timestamps, and visible engagement as normalized account-linked records.

- **Request:** `POST https://api.socq.ai/v1/tiktok/user-videos`
- **publicId:** `tiktok/user-videos`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-25
- **Example body:** [`payloads/user-videos.json`](payloads/user-videos.json)

Collect public videos posted by TikTok users. Results are normalized and billed by the actual saved record count.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `region` | string | No | - |
| `results_limit` | integer | No | (value 20 to 2000; default `100`) |
| `sort_by` | string | No | - |
| `usernames` | array of string | Yes | Public account usernames. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/user-videos" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "usernames": [
    "@tiktok"
  ],
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/user-videos](https://docs.socq.ai/api-manual/tiktok/user-videos) · Landing page: [socq.ai/apis/tiktok/user-videos](https://socq.ai/apis/tiktok/user-videos?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Live Room Info API

Retrieve a point-in-time public TikTok live room snapshot from its room and owner IDs, including title, status, owner identity, cover image, viewer count, and like count.

- **Request:** `POST https://api.socq.ai/v1/tiktok/live-room-info`
- **publicId:** `tiktok/live-room-info`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-27
- **Example body:** [`payloads/live-room-info.json`](payloads/live-room-info.json)

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `room_id` | string | Yes | A public live room identifier. |
| `user_id` | string | Yes | A public account identifier. |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/live-room-info" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "room_id": "7523685855395842871",
  "user_id": "6742945285876515845"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/live-room-info](https://docs.socq.ai/api-manual/tiktok/live-room-info) · Landing page: [socq.ai/apis/tiktok/live-room-info](https://socq.ai/apis/tiktok/live-room-info?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Trending Feed API

Collect the current public TikTok video feed for a region code, returning video IDs, captions, creators, cover images, timestamps, and visible engagement.

- **Request:** `POST https://api.socq.ai/v1/tiktok/trending-feed`
- **publicId:** `tiktok/trending-feed`
- **Price:** 0.7 credits ($0.0035) per result
- **Launched:** 2026-07-27
- **Example body:** [`payloads/trending-feed.json`](payloads/trending-feed.json)

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `region` | string | Yes | - |
| `results_limit` | integer | No | (value 4 to 2000) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/trending-feed" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "region": "US",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/trending-feed](https://docs.socq.ai/api-manual/tiktok/trending-feed) · Landing page: [socq.ai/apis/tiktok/trending-feed](https://socq.ai/apis/tiktok/trending-feed?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Video Transcript API

Extract transcripts from public TikTok video URLs with an optional language, returning text, language, format, source links, and collection time as normalized records.

- **Request:** `POST https://api.socq.ai/v1/tiktok/video-transcript`
- **publicId:** `tiktok/video-transcript`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-07-27
- **Example body:** [`payloads/video-transcript.json`](payloads/video-transcript.json)

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `language` | string | No | - |
| `urls` | array of string | Yes | Public profile or content URLs. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/video-transcript" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "urls": [
    "https://www.tiktok.com/@creator/video/VIDEO_ID"
  ],
  "language": "en"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/video-transcript](https://docs.socq.ai/api-manual/tiktok/video-transcript) · Landing page: [socq.ai/apis/tiktok/video-transcript](https://socq.ai/apis/tiktok/video-transcript?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Search Users API

Search public TikTok creators and accounts by keyword, returning normalized identity, biography, account flags, and visible follower, following, and video counts.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search-users`
- **publicId:** `tiktok/search-users`
- **Price:** 0.6 credits ($0.003) per result
- **Launched:** 2026-09-11
- **Example body:** [`payloads/search-users.json`](payloads/search-users.json)

Search public TikTok creators and accounts by keyword to collect normalized profile identity and metrics.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `query` | string | Yes | Search query. |
| `results_limit` | integer | No | (value 1 to 2000; default `100`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search-users" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "taylor swift",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search-users](https://docs.socq.ai/api-manual/tiktok/search-users) · Landing page: [socq.ai/apis/tiktok/search-users](https://socq.ai/apis/tiktok/search-users?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Song API

Collect detailed public TikTok sound and music metadata by clip ID or sound URL, returning author, album, duration, audio links, and video usage count.

- **Request:** `POST https://api.socq.ai/v1/tiktok/song`
- **publicId:** `tiktok/song`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-09-11
- **Example body:** [`payloads/song.json`](payloads/song.json)

Collect detailed public TikTok sound and music metadata by clip ID or sound URL.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `music_id` | string | One of* | TikTok sound clip ID from a music URL. |
| `url` | string | One of* | A public content or product URL. |

*Required rule: send at least one of `music_id`, `url`.

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/song" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "music_id": "7439295283975702544"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/song](https://docs.socq.ai/api-manual/tiktok/song) · Landing page: [socq.ai/apis/tiktok/song](https://socq.ai/apis/tiktok/song?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Song Videos API

Collect public TikTok videos that use a specific sound, returning normalized video metadata, creator details, captions, media links, and engagement counters.

- **Request:** `POST https://api.socq.ai/v1/tiktok/song-videos`
- **publicId:** `tiktok/song-videos`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-09-11
- **Example body:** [`payloads/song-videos.json`](payloads/song-videos.json)

Collect public TikTok videos that use a specific sound clip ID.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `music_ids` | array of string | Yes | TikTok sound clip IDs from music URLs. (items at least 1) |
| `results_limit` | integer | No | (value 1 to 2000; default `100`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/song-videos" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "music_ids": [
    "7439295283975702544"
  ],
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/song-videos](https://docs.socq.ai/api-manual/tiktok/song-videos) · Landing page: [socq.ai/apis/tiktok/song-videos](https://socq.ai/apis/tiktok/song-videos?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Popular Songs API

Get the TikTok Top 50 or Viral 50 songs chart, with track names, artists, sound IDs and available video counts to help you build a music list for review.

- **Request:** `POST https://api.socq.ai/v1/tiktok/popular-songs`
- **publicId:** `tiktok/popular-songs`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-10-16
- **Example body:** [`payloads/popular-songs.json`](payloads/popular-songs.json)

Choose the TikTok app Top 50 or Viral 50 songs chart. Submit an asynchronous task, then read its standard results.

Get the TikTok app Top 50 or Viral 50 songs chart. chart_type defaults to top; choose viral for Viral 50. results_limit defaults to 20 and accepts integers from 1 to 50. Optionally provide callback_url to receive a task completion notification.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `chart_type` | string | No | TikTok App music chart: top for Top 50, viral for Viral 50. (one of `top`, `viral`; default `"top"`) |
| `results_limit` | integer | No | (value 1 to 50; default `20`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/popular-songs" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "chart_type": "top",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/popular-songs](https://docs.socq.ai/api-manual/tiktok/popular-songs) · Landing page: [socq.ai/apis/tiktok/popular-songs](https://socq.ai/apis/tiktok/popular-songs?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Top Search API

Search TikTok videos and photo carousels by keyword, with captions, creator details, media links and engagement counts returned together in one JSON list.

- **Request:** `POST https://api.socq.ai/v1/tiktok/top-search`
- **publicId:** `tiktok/top-search`
- **Price:** 0.7 credits ($0.0035) per result
- **Launched:** 2026-10-16
- **Example body:** [`payloads/top-search.json`](payloads/top-search.json)

Submit an asynchronous task, then read its standard results.

query is required. results_limit defaults to 100. Results can contain videos and photo carousels; region changes content availability and does not guarantee geographic filtering.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `published_within` | string | No | (one of `day`, `month`, `six_months`, `three_months`, `week`) |
| `query` | string | Yes | Search query. |
| `region` | string | No | (pattern `^[A-Za-z]{2}$`) |
| `results_limit` | integer | No | (value 1 to 2000; default `100`) |
| `sort_by` | string | No | (one of `date`, `likes`, `relevance`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/top-search" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "coffee",
  "sort_by": "relevance",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/top-search](https://docs.socq.ai/api-manual/tiktok/top-search) · Landing page: [socq.ai/apis/tiktok/top-search](https://socq.ai/apis/tiktok/top-search?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok User Live API

Check whether public TikTok accounts are live by username, returning live or offline status and available room details for multiple accounts in one request.

- **Request:** `POST https://api.socq.ai/v1/tiktok/user-live`
- **publicId:** `tiktok/user-live`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-10-16
- **Example body:** [`payloads/user-live.json`](payloads/user-live.json)

Submit an asynchronous task, then read its standard results.

Provide a non-empty usernames array. Each successful lookup returns one billable status, including is_live=false for offline accounts.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `usernames` | array of string | Yes | Public account usernames. (items at least 1) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/user-live" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "usernames": [
    "thejustalex"
  ]
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/user-live](https://docs.socq.ai/api-manual/tiktok/user-live) · Landing page: [socq.ai/apis/tiktok/user-live](https://socq.ai/apis/tiktok/user-live?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Audience Demographics API

Retrieve the country breakdown of a public TikTok account's followers by username, returning each country's name, ISO code, audience share, and sampled follower count.

- **Request:** `POST https://api.socq.ai/v1/tiktok/user-audience`
- **publicId:** `tiktok/user-audience`
- **Price:** 20 credits ($0.10) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/user-audience.json`](payloads/user-audience.json)

See where a TikTok creator's followers live. The result lists every country in the follower sample with its share of the audience and the number of sampled followers behind it, ordered from the largest market down. Run it before booking a collaboration to check that the creator's reach lands in the market you sell to.

username is required. Returns one result for the account with its follower countries, largest share first. Each request is billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `username` | string | Yes | TikTok username, with or without the leading @. (pattern `^@?[A-Za-z0-9_.]{2,24}$`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/user-audience" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "username": "khaby.lame"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/user-audience](https://docs.socq.ai/api-manual/tiktok/user-audience) · Landing page: [socq.ai/apis/tiktok/user-audience](https://socq.ai/apis/tiktok/user-audience?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Similar Accounts API

Find public TikTok accounts that TikTok recommends as similar to a username, returning handles, display names, bios, follower and video counts, and verification status.

- **Request:** `POST https://api.socq.ai/v1/tiktok/similar-users`
- **publicId:** `tiktok/similar-users`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/similar-users.json`](payloads/similar-users.json)

Start from one creator and get the accounts TikTok itself recommends as similar, with follower counts, video counts, bios and verification status. When a creator already performs well for you, this is the quickest way to widen the shortlist around them.

username is required. results_limit defaults to 30 and accepts 1 to 300; accounts arrive in TikTok's recommendation order.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 1 to 300; default `30`) |
| `username` | string | Yes | TikTok username, with or without the leading @. (pattern `^@?[A-Za-z0-9_.]{2,24}$`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/similar-users" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "username": "khaby.lame",
  "results_limit": 30
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/similar-users](https://docs.socq.ai/api-manual/tiktok/similar-users) · Landing page: [socq.ai/apis/tiktok/similar-users](https://socq.ai/apis/tiktok/similar-users?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Reposts API

Collect the videos a public TikTok account has reposted from its username, returning each video's caption, original author, views, likes, hashtags, and video file.

- **Request:** `POST https://api.socq.ai/v1/tiktok/user-reposts`
- **publicId:** `tiktok/user-reposts`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/user-reposts.json`](payloads/user-reposts.json)

Reposts show what an account amplifies beyond its own uploads. This endpoint returns the videos a user has reposted, each with its original author, caption, view and like counts, hashtags and video file, so you can see which creators and topics an account chooses to pass on to its followers.

username is required. Reposts come back newest first; results_limit defaults to 20 and accepts 1 to 500. An account with no reposts returns an empty result, which is not charged.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 1 to 500; default `20`) |
| `username` | string | Yes | TikTok username, with or without the leading @. (pattern `^@?[A-Za-z0-9_.]{2,24}$`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/user-reposts" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "username": "mrbeast",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/user-reposts](https://docs.socq.ai/api-manual/tiktok/user-reposts) · Landing page: [socq.ai/apis/tiktok/user-reposts](https://socq.ai/apis/tiktok/user-reposts?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Playlists API

List the public playlists of a TikTok account by username, returning each playlist's ID, name, link, cover image, video count, and owner details.

- **Request:** `POST https://api.socq.ai/v1/tiktok/user-playlists`
- **publicId:** `tiktok/user-playlists`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/user-playlists.json`](payloads/user-playlists.json)

Creators group their videos into playlists for series, tutorials and recurring formats. This endpoint lists a user's public playlists with the playlist name, cover and how many videos each one holds, which reveals how a creator organizes their catalog and which formats they keep coming back to.

username is required. results_limit defaults to 20 and accepts 1 to 100. An account without public playlists returns an empty result, which is not charged.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 1 to 100; default `20`) |
| `username` | string | Yes | TikTok username, with or without the leading @. (pattern `^@?[A-Za-z0-9_.]{2,24}$`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/user-playlists" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "username": "zachking"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/user-playlists](https://docs.socq.ai/api-manual/tiktok/user-playlists) · Landing page: [socq.ai/apis/tiktok/user-playlists](https://socq.ai/apis/tiktok/user-playlists?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Hashtag Views API

Look up as many as 20 TikTok hashtags in one request, returning each hashtag's ID, link, total video count, and total views for side-by-side comparison.

- **Request:** `POST https://api.socq.ai/v1/tiktok/hashtag-detail`
- **publicId:** `tiktok/hashtag-detail`
- **Price:** 0.5 credits ($0.0025) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/hashtag-detail.json`](payloads/hashtag-detail.json)

Measure how big a hashtag is on TikTok: the total number of videos posted with it and their combined views. Send up to 20 hashtags in one request and compare the candidates side by side before you settle on the tags for a campaign.

hashtags is required: 1 to 20 hashtag names, with or without #. Each hashtag that exists returns one result and is billed per result; hashtags that do not exist are skipped.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `hashtags` | array of string | Yes | Hashtag names with or without the # prefix, up to 20 per request. (items 1 to 20) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/hashtag-detail" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "hashtags": [
    "cooking",
    "booktok"
  ]
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/hashtag-detail](https://docs.socq.ai/api-manual/tiktok/hashtag-detail) · Landing page: [socq.ai/apis/tiktok/hashtag-detail](https://socq.ai/apis/tiktok/hashtag-detail?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Sound Search API

Search TikTok's sound library by keyword, returning sound IDs, titles, artists, cover art, durations, playable previews, and how many videos use each sound.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search-music`
- **publicId:** `tiktok/search-music`
- **Price:** 0.6 credits ($0.003) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/search-music.json`](payloads/search-music.json)

Search TikTok's sound library by song title, artist or mood. Each result carries the sound's cover, duration, a playable preview and the number of videos already using it, so you can spot sounds that are picking up momentum, or confirm a track's ID before collecting its videos with TikTok Song Videos.

query is required. sort_by orders results by relevance (default), most_used or latest, and region (default US) picks the market to search. results_limit defaults to 20 and accepts 1 to 500.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `query` | string | Yes | Song title, artist or sound name to search for. |
| `region` | string | No | Two-letter country code of the TikTok market to search. (pattern `^[A-Za-z]{2}$`; default `"US"`) |
| `results_limit` | integer | No | (value 1 to 500; default `20`) |
| `sort_by` | string | No | Order of the results: relevance, most_used or latest. (one of `latest`, `most_used`, `relevance`; default `"relevance"`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search-music" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "lofi",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search-music](https://docs.socq.ai/api-manual/tiktok/search-music) · Landing page: [socq.ai/apis/tiktok/search-music](https://socq.ai/apis/tiktok/search-music?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Live Search API

Search TikTok LIVE streams broadcasting now by keyword, returning room IDs, stream titles, hosts, current viewers, likes, and start times, ready for product lookups.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search-live`
- **publicId:** `tiktok/search-live`
- **Price:** 0.6 credits ($0.003) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/search-live.json`](payloads/search-live.json)

Find LIVE streams that are on air right now for a keyword. Results include the stream title, host, current viewers, likes and start time. Each result's `id` and `author.id` are exactly the `room_id` and `user_id` that TikTok Live Shopping takes, so a shopping stream you find here leads straight to the products it is selling.

query is required. Results cover streams broadcasting at the time of the request. results_limit defaults to 20 and accepts 1 to 200.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `query` | string | Yes | Keyword to find LIVE streams for. |
| `results_limit` | integer | No | (value 1 to 200; default `20`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search-live" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "deals",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search-live](https://docs.socq.ai/api-manual/tiktok/search-live) · Landing page: [socq.ai/apis/tiktok/search-live](https://socq.ai/apis/tiktok/search-live?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Photo Search API

Search TikTok photo carousel posts by keyword, returning every slideshow image along with captions, authors, hashtags, views, likes, comments, and shares.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search-photos`
- **publicId:** `tiktok/search-photos`
- **Price:** 0.6 credits ($0.003) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/search-photos.json`](payloads/search-photos.json)

Search TikTok's photo carousel posts on their own, with videos left out of the results. Every result includes all images in the carousel plus its caption, author, hashtags and engagement counts, which suits visual research for fashion, food, travel and product inspiration.

query is required. results_limit defaults to 20 and accepts 1 to 500.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `query` | string | Yes | Keyword to find photo posts for. |
| `results_limit` | integer | No | (value 1 to 500; default `20`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search-photos" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "query": "outfit ideas",
  "results_limit": 20
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search-photos](https://docs.socq.ai/api-manual/tiktok/search-photos) · Landing page: [socq.ai/apis/tiktok/search-photos](https://socq.ai/apis/tiktok/search-photos?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Trending Searches API

Collect today's trending searches on TikTok in a single call, returning about 100 search phrases in TikTok's ranked order with a ready-made search link for each.

- **Request:** `POST https://api.socq.ai/v1/tiktok/trending-keywords`
- **publicId:** `tiktok/trending-keywords`
- **Price:** 0.5 credits ($0.0025) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/trending-keywords.json`](payloads/trending-keywords.json)

Get today's trending searches on TikTok in the order TikTok shows them. The list refreshes daily, so it works well as a morning feed for content ideas, reactive posts and keyword tracking.

Takes no input. Returns today's trending searches, usually around 100, ranked in TikTok's order. Each request is billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/trending-keywords" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/trending-keywords](https://docs.socq.ai/api-manual/tiktok/trending-keywords) · Landing page: [socq.ai/apis/tiktok/trending-keywords](https://socq.ai/apis/tiktok/trending-keywords?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Creator Search Insights API

Retrieve popular TikTok searches from Creator Search Insights, returning each search's popularity score, seven-point trend, related video count, category, and labels.

- **Request:** `POST https://api.socq.ai/v1/tiktok/search-insights`
- **publicId:** `tiktok/search-insights`
- **Price:** 1 credit ($0.005) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/search-insights.json`](payloads/search-insights.json)

See what people search for on TikTok and which way the interest is moving. Each search comes with a 0–100 popularity score, a seven-point trend line and the number of related videos. Set `filter_by` to `content_gap` to surface searches with strong demand and few videos so far, a reliable starting point for content planning.

All fields are optional. language (default en), category and filter_by (all or content_gap) shape the list. Each request returns 20 searches and is billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `category` | string | No | Limit the searches to one content category. (one of `fashion`, `food`, `gaming`, `science`, `sports`, `tourism`) |
| `filter_by` | string | No | all for popular searches, or content_gap for searches that have few videos yet. (one of `all`, `content_gap`; default `"all"`) |
| `language` | string | No | Language of the searches to return. (one of `ar`, `de`, `en`, `es`, `fr`, `id`, `ja`, `ko`, `pt`, `th`, `tr`, `vi`; default `"en"`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/search-insights" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "language": "en",
  "category": "food",
  "filter_by": "content_gap"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/search-insights](https://docs.socq.ai/api-manual/tiktok/search-insights) · Landing page: [socq.ai/apis/tiktok/search-insights](https://socq.ai/apis/tiktok/search-insights?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Live Ranking API

Collect TikTok's LIVE daily creator ranking in one call, returning up to 99 hosts with their rank, gift-based score, username, display name, and follower count.

- **Request:** `POST https://api.socq.ai/v1/tiktok/live-ranking`
- **publicId:** `tiktok/live-ranking`
- **Price:** 0.5 credits ($0.0025) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/live-ranking.json`](payloads/live-ranking.json)

Read TikTok's LIVE daily ranking: the day's top creators by the gifts their streams received, each with rank, score and follower count. Checking it at a few points in the day shows who is leading LIVE gifting and how quickly the order shifts.

Takes no input. Returns up to 99 creators from the current daily ranking. Each request is billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/live-ranking" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/live-ranking](https://docs.socq.ai/api-manual/tiktok/live-ranking) · Landing page: [socq.ai/apis/tiktok/live-ranking](https://socq.ai/apis/tiktok/live-ranking?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Live Shopping API

Collect the products in a TikTok LIVE stream's shopping bag from its room and host IDs, returning titles, current prices, units sold, seller IDs, and product images.

- **Request:** `POST https://api.socq.ai/v1/tiktok/live-products`
- **publicId:** `tiktok/live-products`
- **Price:** 0.1 credits ($0.0005) per result
- **Launched:** 2026-11-17
- **Example body:** [`payloads/live-products.json`](payloads/live-products.json)

List what a TikTok LIVE stream is selling. For a stream with a shopping bag, every product comes with its title, current price, units sold, seller and product image. While the stream is on air, take `room_id` and `user_id` from a TikTok Live Search result.

room_id and user_id are required; use the id and author.id of a TikTok Live Search result. results_limit defaults to 100 and accepts 1 to 500. A stream without products returns an empty result, which is not charged.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `results_limit` | integer | No | (value 1 to 500; default `100`) |
| `room_id` | string | Yes | Numeric ID of the LIVE room. (pattern `^\\d{10,32}$`) |
| `user_id` | string | Yes | Numeric TikTok user ID of the LIVE host. (pattern `^\\d{5,32}$`) |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/live-products" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "room_id": "7704767945901132575",
  "user_id": "7153432386608251946",
  "results_limit": 100
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/live-products](https://docs.socq.ai/api-manual/tiktok/live-products) · Landing page: [socq.ai/apis/tiktok/live-products](https://socq.ai/apis/tiktok/live-products?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Fake Views Checker API

Check a public TikTok video URL for fake views, returning a fake-view score, estimated fake views and their share, the traffic tier reached, and the main reason found.

- **Request:** `POST https://api.socq.ai/v1/tiktok/fake-views`
- **publicId:** `tiktok/fake-views`
- **Price:** 5 credits ($0.025) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/fake-views.json`](payloads/fake-views.json)

Estimate how much of a video's view count is inauthentic. The analysis returns a fake-view score, the estimated number and share of fake views, the traffic tier the video reached and the main reason behind the verdict. It is a fast check on sponsored posts and on creators you are about to pay for reach.

url is required. category (default general) tunes the engagement benchmarks to the type of content. Returns one analysis per video, billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `category` | string | No | Content type used to pick engagement benchmarks: general, entertainment, education, product or verified_large. (one of `education`, `entertainment`, `general`, `product`, `verified_large`; default `"general"`) |
| `url` | string | Yes | TikTok video or photo post URL, such as https://www.tiktok.com/@user/video/1234567890123456789. |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/fake-views" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "url": "https://www.tiktok.com/@tiktok/video/7460937381265411370"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/fake-views](https://docs.socq.ai/api-manual/tiktok/fake-views) · Landing page: [socq.ai/apis/tiktok/fake-views](https://socq.ai/apis/tiktok/fake-views?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

### TikTok Comment Keywords API

Extract the keywords that come up most in a public TikTok video's comments from its URL, returning ranked keywords, each with the comments and likes behind it.

- **Request:** `POST https://api.socq.ai/v1/tiktok/comment-keywords`
- **publicId:** `tiktok/comment-keywords`
- **Price:** 1 credit ($0.005) per call
- **Launched:** 2026-11-17
- **Example body:** [`payloads/comment-keywords.json`](payloads/comment-keywords.json)

Find out what a video's audience keeps talking about. The endpoint picks out the keywords that come up most often in the comments and returns each one with the comments that mention it, so the main themes of a busy comment section are readable at a glance.

url is required. Returns the most frequent comment keywords, ranked, each with the comments that mention it. Each request is billed once.

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `callback_url` | string (uri) | No | - |
| `url` | string | Yes | TikTok video or photo post URL, such as https://www.tiktok.com/@user/video/1234567890123456789. |

```bash
curl -X POST "https://api.socq.ai/v1/tiktok/comment-keywords" \
  -H "Authorization: Bearer $SOCQ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "url": "https://www.tiktok.com/@tiktok/video/7460937381265411370"
}'
```

Full docs: [https://docs.socq.ai/api-manual/tiktok/comment-keywords](https://docs.socq.ai/api-manual/tiktok/comment-keywords) · Landing page: [socq.ai/apis/tiktok/comment-keywords](https://socq.ai/apis/tiktok/comment-keywords?utm_source=github&utm_medium=readme&utm_campaign=socq-tiktok-api)

## Repository contents

| Path | Purpose |
| --- | --- |
| [`examples/curl/socq.sh`](examples/curl/socq.sh) | Submit, poll and paginate with cURL and jq |
| [`examples/node/socq.mjs`](examples/node/socq.mjs) | Same workflow in Node.js 20+ (no dependencies) |
| [`examples/python/socq.py`](examples/python/socq.py) | Same workflow in Python 3.8+ (standard library) |
| [`payloads/`](payloads) | One documented request body per endpoint |
| [`endpoints.json`](endpoints.json) | Endpoint list, prices and request schemas used by the scripts and checks |
| [`fixtures/`](fixtures) | Synthetic submit and task response shapes |
| [`docs/production-notes.md`](docs/production-notes.md) | Retries, timeouts, pagination and data handling |
| [`scripts/check.mjs`](scripts/check.mjs) | Offline check: payloads, syntax and secrets |

## Responsible use and platform scope

- Use only publicly accessible TikTok data and the fields supported by each endpoint.
- Do not use the examples to access restricted content, login-only surfaces, authentication controls or non-public personal information.
- SocQ is not an official API of the represented platform and is not affiliated with or endorsed by it. Platform names and trademarks belong to their respective owners.
- Before production use, assess the laws, platform terms, privacy obligations and retention requirements that apply to your organization and use case.
- Collect only the fields needed for a defined purpose, restrict access, set retention periods, and support correction or deletion workflows where required.

This section describes the public-data boundary; it is not legal advice.

## License

[MIT](LICENSE)
