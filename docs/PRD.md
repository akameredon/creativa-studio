# Creativa Studio — Product Requirements Document

**Version:** 1.0  
**Status:** Approved product direction; implementation pending  
**Product model:** Free core forever  
**Ambition:** Full creative platform  
**Reference:** SaidCard Studio, expanded into a professional visual content production environment

## 1. Vision
Make professional visual communication accessible to everyone. Creativa Studio helps individuals, creators, businesses, marketers, agencies, educators, and designers create, edit, organize, and export professional visual content without requiring expensive software or design expertise.

## 2. Product principles
1. Permanent free core for essential manual design.
2. No mandatory subscription.
3. No watermark on user-created exports.
4. No compulsory AI credits for ordinary design.
5. Projects remain editable and user-controlled.
6. Mobile-first, desktop-capable experience.
7. AI enhances rather than replaces human control.
8. Transparent limitations, costs, and provider dependencies.
9. Privacy-conscious defaults and secure project ownership.
10. No fake controls or claims of unfinished features.

## 3. Target users
- Social media creators
- Small businesses and entrepreneurs
- Digital marketers and agencies
- Professional graphic designers
- Educators and community organizations
- Event organizers
- Personal brands and content publishers

## 4. Product modules

### 4.1 Professional design editor — foundational
- Freeform canvas and custom dimensions
- Text, image, shape, line, and background objects
- Move, resize, rotate, crop, align, duplicate, group, and delete
- Layer ordering, visibility, lock, and rename
- Undo/redo and keyboard shortcuts
- Zoom, smart guides, and optional grid snapping
- Typography controls: family, size, weight, alignment, spacing, colour, outline, shadow
- Image controls: crop, position, opacity, brightness, contrast, saturation, blur
- Save, reopen, autosave, and draft recovery

### 4.2 Format presets
Initial presets: Instagram square 1080×1080; Instagram portrait 1080×1350; Story/Reel 1080×1920; Facebook landscape 1200×630; YouTube thumbnail 1280×720; LinkedIn landscape 1200×627; Pinterest pin 1000×1500; custom dimensions.

Treat dimensions as editable presets, not hard-coded limitations. Print workflows must explicitly configure physical dimensions and DPI.

### 4.3 Social media studio
- Quote-card creator
- Platform-specific templates
- Promotional, educational, personal-brand, event, product, and commentary categories
- Social-post mockups must not falsely imply authenticity or platform verification

### 4.4 Carousel builder
- Multi-page documents
- Add, duplicate, delete, reorder slides
- Shared theme and brand consistency
- Per-slide editing and export
- PDF export
- AI-assisted article-to-carousel workflow in a later phase

### 4.5 Brand kits
- Multiple brands per user
- Logo assets and variations
- Primary, secondary, and accent colours
- Typography and guidelines
- Apply brand settings to new and existing designs

### 4.6 AI creative assistant
- Prompt-to-editable-design proposals
- Copy, headlines, captions, calls to action
- Layout suggestions and design transformations
- Optional image generation and background removal through replaceable providers
- Structured, schema-validated output only
- Never execute arbitrary AI-generated HTML or JavaScript
- Paid provider calls require clear user-facing disclosure and authorization

### 4.7 Bulk design generation
- CSV and spreadsheet input
- Field mapping to template variables
- Variable text and images
- Preview, validation, and batch export
- No silent paid usage

### 4.8 Templates and assets
- Searchable editable templates
- Categories, dimensions, previews, authorship, and licensing
- Icons, shapes, illustrations, backgrounds, patterns, frames, and uploaded assets
- Track license and attribution metadata

### 4.9 Projects and content planning
- Projects, folders, drafts, recent work, archive/restore
- Version history and recovery
- Content calendar with draft/planned/published states
- Captions and design attachments

### 4.10 Future collaboration and marketplace
- Sharing, viewer/editor roles, comments, team workspaces
- Creator-published templates, assets, packs, and brand kits
- Licensing and creator attribution
- These are later-phase modules, not first-release blockers

## 5. User experience
### Dashboard
Quick create, recent projects, format shortcuts, templates, AI entry point, and brand-kit access.

### Desktop editor
Left tool/library panel, central canvas, right contextual properties, top command toolbar, and page/slide strip where relevant.

### Mobile editor
Full-screen canvas, touch-friendly contextual controls, collapsible panels, bottom toolbar, and straightforward save/export actions. Do not simply shrink the desktop interface.

## 6. Export requirements
Initial formats: PNG and JPG. Later: SVG where safe/compatible, WebP, and PDF. Support transparent backgrounds, custom dimensions, high-resolution rendering, multipage documents, and batch export. Verify exports against canvas state for clipping, missing assets, font substitution, and alignment errors.

## 7. Free-core boundary
Permanent free core includes manual editor, basic templates, text and image editing, shapes, basic brand kits, basic carousel creation, project saving, PNG/JPG export, custom canvas dimensions, and no compulsory watermark.

Potential optional revenue later: premium third-party AI services, marketplace sales, optional asset packs, advanced team features, and managed storage. These are not approved commitments and must not displace core functionality without explicit product approval.

## 8. Non-functional requirements
- Responsive and performant on ordinary mobile devices
- Accessible target: WCAG 2.2 AA
- Keyboard navigation and visible focus
- Secure authentication and row-level authorization
- Private projects by default
- Safe upload validation and server-side authorization
- No client-side secrets or service-role credentials
- Local draft recovery and clear save status
- Graceful operation when AI providers are unavailable

## 9. First release acceptance criteria
A user can create a blank design, choose a preset/custom size, add and edit text, upload and position an image, add shapes/backgrounds, manage layers, undo/redo, save, reload, and export a high-resolution PNG. These actions must work on desktop and mobile. A visible UI control is not considered implemented until its action is tested.

## 10. Explicit non-goals for first release
Marketplace, team billing, social publishing integrations, complex animation, enterprise integrations, and advanced AI image generation must not delay the first working editor.

## 11. Success measures
- A beginner creates a polished graphic without training.
- A designer can edit individual objects.
- A user can save and reopen without data loss.
- Export matches the canvas.
- Core editor works without paid AI.
- Mobile workflows are usable.
- Private projects remain private.
