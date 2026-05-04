# UNIVERSAL DESIGN & ASSET STANDARDS

**UI/UX Aesthetic:**
1. **Context-Driven Design:** There is NO hardcoded palette or style. All design decisions — color palette, typography, layout paradigm, information density, animations, light/dark mode — must be derived from the project's domain, target audience, and purpose.
2. **Architect-Defined Design System:** During the `/architect` phase, analyze the project concept and define a complete design system in `master_blueprint.md`. This includes:
   - Primary, secondary, and accent colors (with hex codes)
   - Typography choices (font families, scale)
   - Layout paradigm (dashboard-dense, consumer-friendly, editorial, etc.)
   - Component style (rounded/sharp, flat/elevated, minimal/rich)
   - Light mode, dark mode, or both
3. **Design Token Centralization:** All design tokens must live in a single source of truth (CSS variables, theme config, or tokens file). No ad-hoc colors or magic numbers in component files.
4. **Component Structure:** Enforce strict centralization of UI components. Reusability is paramount.

**Asset Generation Protocol:**
Whenever a task requires the generation of visual assets (e.g., icons, illustrations, renders), all generated assets must be presented as raw images on a solid white background — no demonstrative or stylized mockups.
