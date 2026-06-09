## Effort Summary (continued)

**Realistic Timeline:**
- **Phase 1 (Foundation):** 4 hours (Steps 1–2 sequential, Coder)
- **Phase 2 (Design & Binding):** 4–6 hours (Steps 3–4 parallel, Designer + Coder)
- **Phase 3 (Developer Experience):** 2 hours (Step 5, Coder, can overlap with Phase 2)
- **Phase 4 (Integration & Testing):** 2–4 hours (Step 6, Orchestrator coordination)
- **Total Estimated Duration:** 10–16 hours (compressed to ~8 hours with full parallelization)

**Recommended Work Cadence:**
- Day 1: Steps 1–2 (Coder foundation)
- Day 1–2: Steps 3–4 in parallel (Designer CSS, Coder JS binding)
- Day 2: Step 5 (Launch config) + Step 6 (Integration testing)

---

## Code Quality & Repository Patterns

### Naming Conventions
- **CSS Classes:** kebab-case (`.project-card`, `.status-badge`, `.progress-bar`)
- **JavaScript Variables:** camelCase (`projectData`, `loadProjects`, `renderCard`)
- **HTML IDs:** kebab-case for semantic elements (`#projects-grid`, `#dashboard-header`)
- **Data Keys in JSON:** camelCase (`projectId`, `targetEndDate`, `teamMembers`)

### File Organization
```
app/
├── index.html           # Markup + inline JS
├── styles.css           # All styling
├── project-data.json    # Sample project data
.vscode/
├── launch.json          # Debug/launch config
docs/
├── project-pulse-plan.md # This implementation plan
```

### Code Style Guidelines
- **HTML:** Valid HTML5, semantic elements (header, main, section), proper nesting
- **CSS:** Mobile-first, logical property order (layout > sizing > typography > effects), no !important unless unavoidable
- **JavaScript:** Async/await for fetch, descriptive function names, comments for complex logic, console clean on production

---

## Success Criteria & Definition of Done

### Project Complete When:

1. ✅ All files created and exist in correct locations:
   - `app/index.html`
   - `app/styles.css`
   - `app/project-data.json`
   - `.vscode/launch.json`

2. ✅ Functionality:
   - Dashboard loads without console errors
   - 4–6 project cards display with all required fields (title, status, progress, team, timeline)
   - Progress bars accurately reflect percentage values
   - Status badges color-code correctly (Active=green, On Hold=yellow, Completed=gray)
   - JSON load error handled gracefully with user-friendly message

3. ✅ Design:
   - Responsive layout works at 320px, 768px, 1024px, and 1440px+ breakpoints
   - No horizontal overflow on mobile
   - Card hover states provide visual feedback
   - All interactive elements have visible focus indicators (keyboard accessible)
   - WCAG AA color contrast ≥4.5:1 for body text, ≥3:1 for UI components

4. ✅ Developer Experience:
   - F5 in Codespace launches dashboard in browser
   - Launch config cwd set to `${workspaceFolder}/app`
   - DevTools debugger attaches successfully (if supported)

5. ✅ Code Quality:
   - HTML validates at W3C Validator (zero errors)
   - CSS validates at W3C CSS Validator (zero errors)
   - JavaScript console clean (no warnings or errors)
   - Code follows repository naming and style patterns
   - Relative file paths used (no absolute paths)

6. ✅ Testing:
   - All manual checks in Step 6 completed and documented
   - Responsive design verified on 3+ devices/viewport sizes
   - Accessibility audit passed (WAVE or Lighthouse ≥80)
   - Error handling tested (JSON missing/malformed)
   - Performance acceptable (load time <2 seconds)

7. ✅ Documentation:
   - Implementation plan finalized and saved to `docs/project-pulse-plan.md`
   - Optional: Brief README or inline code comments for maintenance

---

## Handoff Checklist for Orchestrator

- [ ] Planner delivers this implementation plan (project-pulse-plan.md)
- [ ] Orchestrator reviews plan with Coder and Designer
- [ ] Coder begins Steps 1–2 (data + HTML)
- [ ] Designer begins Step 3 (CSS) in parallel with Coder Step 2
- [ ] Coder completes Step 4 (JavaScript binding)
- [ ] Coder completes Step 5 (launch config)
- [ ] Orchestrator coordinates Step 6 (E2E testing and validation)
- [ ] All validation criteria met; sign-off documented
- [ ] Learner commits all changes via Copilot CLI
- [ ] Dashboard ready for deployment/presentation

---

## Appendix: Sample JSON Structure Reference

**project-data.json Example:**
```json
{
  "projects": [
    {
      "id": "PRJ001",
      "title": "Q3 Mobile Redesign",
      "description": "Complete redesign of mobile app UX/UI with new navigation and accessibility improvements",
      "status": "Active",
      "progress": 65,
      "team": ["Alice Chen", "Bob Martinez", "Carol Lopez"],
      "startDate": "2026-04-01",
      "targetEndDate": "2026-07-15",
      "milestone": "Design review completed",
      "priority": "High"
    },
    {
      "id": "PRJ002",
      "title": "Backend API Refactor",
      "description": "Migrate legacy REST API to GraphQL with improved performance and caching",
      "status": "Active",
      "progress": 42,
      "team": ["David Kim", "Emma Wilson", "Frank Patel", "Grace O'Brien"],
      "startDate": "2026-05-15",
      "targetEndDate": "2026-09-30",
      "milestone": "GraphQL schema finalized",
      "priority": "High"
    },
    {
      "id": "PRJ003",
      "title": "Security Audit & Compliance",
      "description": "Conduct full security audit, implement SOC 2 compliance requirements",
      "status": "On Hold",
      "progress": 28,
      "team": ["Henry Yamamoto", "Iris Johnson"],
      "startDate": "2026-06-01",
      "targetEndDate": "2026-08-15",
      "milestone": "Vulnerability assessment pending",
      "priority": "High"
    },
    {
      "id": "PRJ004",
      "title": "Documentation Portal",
      "description": "Build searchable knowledge base and API documentation site",
      "status": "Active",
      "progress": 78,
      "team": ["Jack Thompson", "Kelly Anderson", "Liam Chen"],
      "startDate": "2026-03-15",
      "targetEndDate": "2026-07-01",
      "milestone": "First draft ready for review",
      "priority": "Medium"
    },
    {
      "id": "PRJ005",
      "title": "Customer Analytics Dashboard",
      "description": "Real-time analytics dashboard for customer behavior tracking and insights",
      "status": "Active",
      "progress": 51,
      "team": ["Maya Patel", "Nathan Brooks"],
      "startDate": "2026-05-01",
      "targetEndDate": "2026-08-31",
      "milestone": "Data pipeline integration complete",
      "priority": "Medium"
    },
    {
      "id": "PRJ006",
      "title": "Mobile App v2.0 Release",
      "description": "Major release with new features, performance improvements, and bug fixes",
      "status": "Completed",
      "progress": 100,
      "team": ["Olivia Richardson", "Peter Zhang", "Quinn Murphy", "Rachel Green", "Samuel Davis"],
      "startDate": "2026-01-15",
      "targetEndDate": "2026-06-01",
      "milestone": "Shipped to production",
      "priority": "High"
    }
  ]
}
```

---

## Appendix: CSS Design Tokens Reference

**Recommended Color Palette:**
```css
:root {
  /* Primary Colors */
  --color-primary: #1f883d;      /* GitHub Green */
  --color-secondary: #0969da;    /* GitHub Blue */
  --color-accent: #fb8500;       /* Warm Orange */
  
  /* Status Colors */
  --color-status-active: #1a7f37;      /* Green for Active */
  --color-status-on-hold: #d4a574;     /* Amber for On Hold */
  --color-status-completed: #6e7781;   /* Gray for Completed */
  
  /* Utility Colors */
  --color-success: #1a7f37;
  --color-warning: #d4a574;
  --color-error: #da3633;
  --color-neutral: #f6f8fa;
  
  /* Grayscale */
  --color-text-primary: #24292f;
  --color-text-secondary: #656d76;
  --color-border: #d0d7de;
  --color-bg-light: #ffffff;
  --color-bg-muted: #f6f8fa;
  
  /* Typography */
  --font-primary: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;
  --font-size-sm: 0.875rem;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.5rem;
  --font-size-2xl: 2rem;
  
  /* Spacing */
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 1.5rem;
  --spacing-xl: 2rem;
  --spacing-2xl: 3rem;
  
  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px rgba(0, 0, 0, 0.1);
  --shadow-hover: 0 20px 25px rgba(0, 0, 0, 0.15);
  
  /* Border Radius */
  --radius-sm: 0.25rem;
  --radius-md: 0.5rem;
  --radius-lg: 0.75rem;
  
  /* Transitions */
  --transition-fast: 150ms ease-in-out;
  --transition-base: 250ms ease-in-out;
  --transition-slow: 350ms ease-in-out;
}
```

---

## Appendix: Accessibility Checklist

- [ ] **Keyboard Navigation:** All interactive elements reachable via Tab key; logical tab order top-to-bottom, left-to-right
- [ ] **Focus Indicators:** Visible focus outline on all focusable elements (buttons, links, inputs, cards if interactive)
- [ ] **Color Contrast:** Text ≥4.5:1 contrast ratio; UI components ≥3:1
- [ ] **Color Independence:** Information not conveyed by color alone; use text labels, icons, patterns
- [ ] **Screen Reader Support:** Semantic HTML, proper heading hierarchy (h1, h2, h3), aria-label for icon-only elements
- [ ] **Form Accessibility:** Labels associated with inputs (for attribute), error messages clear and associated
- [ ] **Responsive Text:** Font sizes scale appropriately at different zoom levels (≥100%, ≤200%)
- [ ] **Motion:** No auto-playing animations; respect prefers-reduced-motion media query if animations included
- [ ] **Touch Targets:** Interactive elements ≥44px × 44px (mobile); sufficient spacing between clickable areas
- [ ] **Language Declaration:** `<html lang="en">` set on root element

**Automated Testing Tools:**
- [WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/) — Browser extension, reports errors/warnings
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) — Verify color contrast ratios
- [Lighthouse](https://developers.google.com/web/tools/lighthouse) — Built into Chrome DevTools, includes accessibility audit
- [axe DevTools](https://www.deque.com/axe/devtools/) — Browser extension, automated accessibility scanning

---

## Appendix: Responsive Breakpoint Testing Checklist

| Viewport | Device | Layout | Test Focus |
|----------|--------|--------|-----------|
| 320px | Mobile (small) | Single column, full width | Typography readability, tap targets ≥44px |
| 375px | Mobile (standard) | Single column | Card overflow, padding balance |
| 768px | Tablet (portrait) | 2-column grid | Grid reflow, spacing consistency |
| 1024px | Tablet (landscape) / Small desktop | 3-column grid | Full feature visibility, max-width container |
| 1440px+ | Desktop | 3–4 column grid | Content centering, edge margins |

**Testing Method:**
- Use DevTools Device Emulation (F12 > Ctrl+Shift+M)
- Manually resize browser window, verify smooth transition at each breakpoint
- Test on real devices if available (physical phone, tablet)
- Check that no content requires horizontal scroll

---

## Appendix: Performance Optimization Checklist

| Metric | Target | How to Measure | Mitigation |
|--------|--------|-----------------|-----------|
| Largest Contentful Paint (LCP) | <2.5s | DevTools Lighthouse | Optimize image size, defer non-critical CSS |
| Cumulative Layout Shift (CLS) | <0.1 | DevTools Lighthouse | Set explicit card heights, reserve space for progress bar |
| First Input Delay (FID) | <100ms | DevTools Performance | Minimize JS blocking, use event listeners efficiently |
| Page Load Time | <2s | DevTools Network | Inline critical CSS, load project-data.json in parallel |
| Bundle Size | <100KB | DevTools Network | No external dependencies for MVP; minify if added later |

**Quick Optimizations:**
- Inline critical CSS (`.dashboard`, `.project-card`) in `<head>`
- Load project-data.json asynchronously with fallback
- Use `defer` attribute on script tags to prevent render blocking
- Minimize use of render-blocking resources

---

## Appendix: Future Enhancements (Post-MVP)

These are documented for learner reference; **not** part of MVP scope:

1. **Interactivity:** Click project card to view full details in modal or detail page
2. **Sorting & Filtering:** Sort by status/priority/progress; search by title or team member
3. **Timeline Visualization:** Gantt chart or timeline component showing project duration
4. **Team Member Profiles:** Clickable avatars with member details, contribution metrics
5. **Real-Time Updates:** WebSocket or polling to refresh project data from live server
6. **Export/Print:** PDF export, print-optimized layout
7. **Dark Mode:** CSS custom properties for light/dark theme toggle
8. **Notifications:** Toast alerts for project status changes
9. **Mobile App:** Wrap in Electron or React Native for desktop/mobile distribution
10. **Localization:** Support for multiple languages (i18n)
11. **Analytics:** Track dashboard usage, view patterns, user engagement
12. **Integration:** Connect to Jira, GitHub Projects, Azure DevOps for live project sync

---

## Sign-Off

**Plan Created By:** Planner (Claude Opus 4.7)  
**Date:** 2026-06-09  
**Status:** Ready for Orchestrator Review & Execution  

**Next Steps:**
1. Orchestrator reviews this plan with Coder and Designer
2. Orchestrator breaks plan into executable phases and assigns to team members
3. Team members execute assigned steps in parallel and sequentially per dependency graph
4. Orchestrator validates completion and coordinates final integration (Step 6)
5. Learner commits all changes and deploys dashboard

---

**End of Implementation Plan**

This document is ready to be saved to `docs/project-pulse-plan.md` and used as the master reference for Mona's Project Pulse dashboard implementation.
