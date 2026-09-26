# habeebk.github.io — Site Maintenance Guide

Live site: **https://habeebk.github.io**

---

## Deploying changes

Any change pushed to the `main` branch goes live automatically via GitHub Pages within 1–2 minutes.

```bash
git add <file>
git commit -m "describe what you changed"
git push
```

---

## Managing events

### Admin panel
**URL:** https://habeebk.github.io/tools/event-admin.html

The admin password is stored in `tools/event-admin.html` (search for `ADMIN_PASSWORD`). Change it directly in the file and push to update it.

### Create an event
1. Open the admin panel and sign in
2. Click the **Create Event** tab
3. Fill in the title, date, time, and location
4. Click **Create Event**

### View registrations
1. Sign in to the admin panel
2. Click any event on the **Events** tab to expand it
3. Registrations are listed with name, gender, mobile, emirate, email, and profession
4. Click **Export CSV** to download the attendee list

### Delete an event
1. Expand the event on the **Events** tab
2. Click **Delete Event** — this also removes all registrations for that event

---

## Updating site content

All content is in `index.html`. No build step is needed — edit the file directly and push.

| What to change | Where in index.html |
|---|---|
| Name / title / tagline | `hero` section |
| About paragraphs | `about` section |
| Expertise cards | `expertise` section |
| Interests list | `interests` section |
| Tools / utilities cards | `utilities` section |

---

## Adding a new tool card

In the `utilities` section of `index.html`, copy an existing card block:

```html
<!-- External link -->
<a href="https://example.com" target="_blank" rel="noopener" class="card card-link">
  <div class="card-icon">🔧</div>
  <h3>Tool Name</h3>
  <p>Short description of what the tool does.</p>
</a>

<!-- Internal page -->
<a href="tools/my-tool.html" class="card card-link">
  <div class="card-icon">🔧</div>
  <h3>Tool Name</h3>
  <p>Short description of what the tool does.</p>
</a>
```

---

## Supabase (database)

The events and registrations are stored in a Supabase project.

- **Project URL:** `https://klypiihizmfyimtdxayn.supabase.co`
- **Dashboard:** https://supabase.com → sign in → select the project
- **Tables:** `events`, `attendees`, `registrations`

The anon key in the HTML files is safe to be public — it is read-only by design and scoped by Row Level Security policies in Supabase.
