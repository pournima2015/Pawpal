# PawPal V2

PawPal is a responsive pet-care web application built with HTML, CSS, JavaScript and Supabase.

## Included

- 16 HTML pages, including the new `index.html` landing page and `sos.html` Animal SOS page
- 11 CSS files matching the project's CSS naming system
- Supabase-backed JavaScript modules
- Supabase Storage upload support for pet photos and medical documents
- Animal SOS direct-contact workflow placeholder for verified rescue data
- Supabase SQL schema and Row Level Security starter policies
- Test page at `test/supabase.html`
- `DESIGN_PROMPTS.md` documenting the approved animation/UI direction

## Important

No Firebase code is used in this build.

Before using the backend, replace the two placeholders in `supabase/config.js` with your Supabase project URL and publishable key.

Then run `supabase/schema.sql` in the Supabase SQL Editor if the tables/buckets are not already created.

Serve the project through VS Code Live Server. Opening HTML directly with `file://` is not recommended because ES module imports require a local web server.

## CSS structure

The project intentionally keeps 11 CSS files:

- adoption.css
- auth.css
- dashboard.css
- food.css
- grooming.css
- health.css
- petcare.css
- pets.css
- profile.css
- sos.css
- style.css

`style.css` is the shared design system. `vets.html`, `editpet.html` and `editprofile.html` use the shared stylesheet instead of introducing extra CSS files.

## Animal SOS data

Do not invent emergency phone numbers. Add only verified rescue teams, bird rescue organizations, animal ambulances and emergency veterinary contacts to the `rescue_contacts` table.


## Nearby location fetching
The Veterinarians, Food, and Adoption pages use the browser's location permission and OpenStreetMap/Overpass data to fetch real nearby services. The SOS page uses only verified rescue contacts stored in Supabase, with latitude/longitude for distance sorting and direct calling. Geolocation works on HTTPS or localhost and requires the user to allow location access.
