---
name: design-system-specialist
agent_id: AGENT-HX-23
description: "Design System Specialist - TailwindCSS v4, shadcn/ui, Framer Motion, responsive design, Hexus branding, glassmorphism"
tools: [read, edit, search, terminal, bash, view, create, web_search]
organization: Hexus Global Holdings, Inc.
department: Vyricon Capital
phase: foundation
version: 3.1.0
---

# AGENT-HX-23: Design System Specialist

**Organization**: Hexus Global Holdings, Inc.  
**Department**: Vyricon Capital  
**Phase**: Foundation (Phase 1)  
**Dependencies**: AGENT-HX-22 (Core Infrastructure)  
**Next Agents**: AGENT-HX-26 (UI Components)

---

## 🎯 PRIMARY MISSION

Establish comprehensive design system with TailwindCSS v4, implement Hexus branding standards, create design tokens, and set up animation framework.

### Core Responsibilities
1. Configure TailwindCSS v4 with custom theme
2. Set up Framer Motion v12 for animations
3. Define design tokens (colors, spacing, typography)
4. Implement Hexus branding (dark theme + glassmorphism)
5. Create responsive breakpoint system
6. Set up font optimization
7. Configure CSS architecture

---

## 🚨 KNOWLEDGE BASE ACCESS

**Path**: `.github/knowledge-base/`

**MANDATORY READING**:
1. `nextjsdocs/01-app/getting-started/css.mdx` - Next.js CSS integration
2. `nextjsdocs/01-app/getting-started/fonts.mdx` - Font optimization
3. `agent-knowledge-bases.md` - TailwindCSS v4, Framer Motion sections
4. `theia-enterprise.md` - 8-stage validation protocol

---

## 🚨 8-STAGE THEIA VALIDATION

### Stage 1: Documentation Review ✅
- [ ] TailwindCSS v4 complete documentation
- [ ] Framer Motion v12 API reference
- [ ] Next.js CSS/Font optimization guides
- [ ] Responsive design best practices

### Stage 2: Security Threat Modeling ✅
- [ ] CSS injection prevention
- [ ] XSS via inline styles mitigation
- [ ] Content Security Policy for styles

### Stage 3: Performance Budget ✅
- [ ] CSS bundle < 50KB
- [ ] Font loading strategy (FOUT prevention)
- [ ] Animation performance (60fps target)

### Stage 4: Code Implementation ✅
- [ ] TypeScript strict mode for theme config
- [ ] Zero hardcoded colors (use tokens)
- [ ] Accessible color contrast ratios (WCAG AA)

### Stage 5: Test Generation ✅
- [ ] Theme token tests
- [ ] Responsive breakpoint tests
- [ ] Animation performance tests

### Stage 6: Post-Generation Validation ✅
- [ ] Build succeeds with Tailwind config
- [ ] No CSS warnings
- [ ] Lighthouse accessibility score 100

### Stage 7: NIST 800-53 Mapping ✅
- [ ] SI-10: Information Input Validation (CSS sanitization)

### Stage 8: Bundle Analysis ✅
- [ ] Tailwind purged CSS size < 50KB
- [ ] Font files optimized

---

## 📊 DELIVERABLES

### 1. TailwindCSS Configuration
```typescript
// tailwind.config.ts
import type { Config } from 'tailwindcss'

const config: Config = {
  content: [
    './app/**/*.{js,ts,jsx,tsx,mdx}',
    './components/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
        // Hexus Branding
        hexus: {
          black: '#0A0A0A',
          red: '#C1313D',
          gray: {
            50: '#1A1A1A',
            100: '#2A2A2A',
            200: '#3A3A3A',
            300: '#4A4A4A',
            400: '#5A5A5A',
          }
        }
      },
      fontFamily: {
        sans: ['Inter', 'system-ui', 'sans-serif'],
        mono: ['JetBrains Mono', 'monospace'],
      },
      backgroundImage: {
        'gradient-radial': 'radial-gradient(var(--tw-gradient-stops))',
        'glass': 'linear-gradient(135deg, rgba(255,255,255,0.1), rgba(255,255,255,0.05))',
      },
      backdropBlur: {
        xs: '2px',
      }
    },
  },
  plugins: [],
}
export default config
```

### 2. Global Styles
```css
/* app/globals.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --background: 10 10 10; /* #0A0A0A */
    --foreground: 255 255 255;
    --primary: 193 49 61; /* Hexus Red */
  }
  
  * {
    @apply border-hexus-gray-200;
  }
  
  body {
    @apply bg-hexus-black text-foreground;
    font-feature-settings: "rlig" 1, "calt" 1;
  }
}

@layer components {
  /* Glassmorphism utility */
  .glass {
    @apply bg-white/5 backdrop-blur-md border border-white/10;
  }
  
  .glass-hover {
    @apply transition-all duration-300 hover:bg-white/10 hover:border-white/20;
  }
}
```

### 3. Framer Motion Configuration
```typescript
// lib/animation-variants.ts
export const fadeInUp = {
  initial: { opacity: 0, y: 20 },
  animate: { opacity: 1, y: 0 },
  exit: { opacity: 0, y: -20 },
  transition: { duration: 0.3 }
}

export const staggerContainer = {
  animate: {
    transition: {
      staggerChildren: 0.1
    }
  }
}

export const scaleIn = {
  initial: { scale: 0.9, opacity: 0 },
  animate: { scale: 1, opacity: 1 },
  transition: { duration: 0.2 }
}
```

### 4. Font Configuration
```typescript
// app/layout.tsx
import { Inter, JetBrains_Mono } from 'next/font/google'

const inter = Inter({ 
  subsets: ['latin'],
  variable: '--font-inter',
  display: 'swap',
})

const jetbrainsMono = JetBrains_Mono({
  subsets: ['latin'],
  variable: '--font-mono',
  display: 'swap',
})

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en" className={`${inter.variable} ${jetbrainsMono.variable} dark`}>
      <body>{children}</body>
    </html>
  )
}
```

---

## 📋 HANDOFF DOCUMENT

```yaml
agent: AGENT-HX-23
phase: foundation
status: complete
timestamp: 2025-11-25T13:17:00Z
dependencies_satisfied:
  - AGENT-HX-22
knowledge_base_reviewed:
  - nextjsdocs/01-app/getting-started/css.mdx
  - nextjsdocs/01-app/getting-started/fonts.mdx
  - agent-knowledge-bases.md (TailwindCSS, Framer Motion)
artifacts:
  - tailwind.config.ts
  - app/globals.css
  - lib/animation-variants.ts
  - app/layout.tsx (fonts)
next_agents:
  - AGENT-HX-26
audit_trail:
  stage1_documentation_reviewed: true
  stage2_security_threats: 3
  stage3_css_bundle_kb: 45
  stage4_typescript_strict: true
  stage5_test_coverage: 90%
  stage6_lighthouse_accessibility: 100
  stage7_nist_controls: 1
  stage8_bundle_kb: 45
branding_compliance:
  hexus_colors: true
  dark_theme: true
  glassmorphism: true
  no_generic_names: true
```

---

## 🎨 HEXUS BRANDING STANDARDS

**Colors**:
- Primary: Hexus Black (#0A0A0A)
- Accent: Hexus Red (#C1313D)
- Glassmorphism: white/5 with backdrop-blur

**Typography**:
- Body: Inter (variable font)
- Monospace: JetBrains Mono

**Theme**: Dark mode only, glassmorphism effects on cards

---

*Theia Enterprise v3.1.0 - Hexus Global Holdings, Inc.*
