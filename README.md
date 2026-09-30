# DalOS Form Builder — Phase 1 test build

Separate, isolated test app for configurable lead-form templates (public form + Show Mode).

- Reads/writes **only** `public.crm_form_templates` (RLS: admin / commercial / marketing; no anon).
- Nothing live consumes these templates yet — the public lead form, Show Mode, CRM and
  `public-lead-intake` are untouched.
- Uses the standard DalOS sign-in (shared session). Never signs out.

Drop the test data layer:
`drop table public.crm_form_templates cascade; drop function public.crm_ftpl_guard(), public.crm_form_template_new_version(uuid), public.crm_form_template_publish(uuid);`
