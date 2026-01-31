# Lost & Found

A static Lost & Found submission site: post lost or found items, browse listings, and get a confirmation after submitting.

## Pages

1. **Home** (`index.html`) – Landing with nav and overview  
2. **Lost items** (`lost.html`) – All submitted lost items  
3. **Found items** (`found.html`) – All submitted found items  
4. **Post item** (`post.html`) – Form: item name, description, location, contact  
5. **Confirmation** (`confirmation.html`) – Shown after a successful form submission  

## Form fields

- **Item name** – Short name/title  
- **Description** – Detailed description  
- **Location** – Where it was lost or found  
- **Contact** – How to reach the poster  

Type (Lost / Found) is chosen via a toggle on the form.

## Flow

1. User fills the form on **Post item**  
2. Client-side validation: all four fields required  
3. On valid submit: data is stored in `localStorage`, the new submission is put in `sessionStorage`, and the user is redirected to **Confirmation**  
4. **Confirmation** reads from `sessionStorage`, shows the submitted details, and offers links to the relevant list, “Post another”, and Home  

## Run locally

- **Option A:** Open `index.html` in a browser.  
- **Option B:** Serve the folder with a static server, e.g.:

  ```bash
  npx serve .
  # or
  python -m http.server 8000
  ```

  Then open `http://localhost:3000` (or `http://localhost:8000`) and use `index.html` as the entry point.

## Storage

- **localStorage** (`lostAndFoundItems`): all submissions (persists across sessions)  
- **sessionStorage** (`lostAndFoundLastSubmission`): last submitted item, used once on the Confirmation page  

No backend or build step; works as plain HTML, CSS, and JavaScript.
