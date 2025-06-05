# Working with Claude Code: Process Guide for Precision Design Implementation

## Overview
This document captures proven methodologies for implementing pixel-perfect designs using Claude Code, based on a successful CRT interface project that demonstrated how precision measurement can eliminate typical AI-assisted development failures.

## Core Process Methodology

### 1. Configuration Before Implementation
**Rule**: Always verify and fix foundational setup before iterating on visual implementation.

**Key Actions**:
- Check framework versions and compatibility (Next.js 15+, Tailwind v4.1+, React 19)
- Verify CSS configuration matches current standards (`@import "tailwindcss"` for v4.1)
- Update PostCSS configuration for current version requirements
- Test that basic utilities (padding, spacing) work before building complex layouts

**Red Flags**: When basic CSS utilities don't work as expected, stop and check configuration rather than continuing to iterate.

### 2. Direct Measurement Over Visual Estimation
**Problem**: AI visual analysis consistently fails at color accuracy, proportion estimation, and structural understanding.

**Solution**: Use design tools (Affinity, Figma, etc.) to get exact pixel measurements.

**Process**:
- Measure actual pixel dimensions in design tools
- Convert to responsive units with precise percentages
- Use exact hex color values, not approximations
- Count and verify all structural elements (dividers, sections, etc.)

**Example**: Instead of "looks like about 25% width" → measure 638px out of 2554px total = exactly 25%

### 3. Structured Layout Implementation
**Approach**: Break complex layouts into precise, measurable components.

**Key Principles**:
- Implement exact spacing using measured values
- Use proper CSS layout techniques (flexbox, grid) with precise proportions
- Test spacing and positioning incrementally
- Verify visual output against reference at each step

### 4. Communication and Debugging Protocol
**For Users**:
- Provide reference images when possible
- Give exact measurements when available
- Be direct about what's wrong vs. what's expected
- Don't accept "close enough" - precision is achievable

**For Claude**:
- Check configuration issues first when basic things don't work
- Describe what you actually implemented vs. what you intended
- Test spacing utilities work before building complex layouts
- Be honest about failures rather than describing intended behavior

## Technical Configuration Standards

### Next.js 15+ Setup
- Use App Router architecture
- Enable Turbopack for development (`--turbopack` flag)
- Async request APIs: `cookies()`, `headers()` are now async
- Be aware of changed caching behavior

### Tailwind CSS v4.1+ Setup
```css
/* globals.css */
@import "tailwindcss";
```

```javascript
// postcss.config.mjs
export default {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};
```

### React 19 Features Available
- `useActionState`, `useOptimistic`, `use` hooks
- Form actions and `useFormStatus`
- Enhanced server components

## Layout Implementation Best Practices

### Responsive Design Approach
1. Measure exact pixel dimensions from reference
2. Calculate precise percentages
3. Use CSS custom properties for repeated values
4. Test responsive behavior at multiple breakpoints

### Spacing and Positioning
- Use exact measurements converted to responsive units
- Implement proper flexbox/grid structure before adding content
- Test that dividers and spacing elements render correctly
- Check layout structure before adding visual styling

### Component Architecture
- Keep components focused and measurable
- Use precise props for spacing and sizing
- Implement exact color values from design specifications
- Test individual components before combining

## Common Pitfalls and Solutions

### Configuration Issues
**Problem**: Basic utilities not working despite correct syntax
**Solution**: Check framework versions and configuration files first

### Visual Estimation Failures
**Problem**: "Looks close enough" leading to compounding inaccuracies
**Solution**: Always measure and use exact values

### Layout Structure Problems
**Problem**: Complex nested layouts with unclear spacing
**Solution**: Build incrementally, test spacing at each level

### Communication Breakdowns
**Problem**: Repeated implementation of wrong specifications
**Solution**: Verify understanding with precise descriptions before coding

## Success Metrics

### Technical Success
- Spacing utilities work correctly with proper configuration
- Layout matches reference design at pixel level
- Responsive behavior maintains proportions across screen sizes
- Components render exactly as specified

### Process Success
- Configuration issues caught and fixed early
- Measurements used instead of visual estimation
- Implementation matches specifications on first attempt
- Refinements are targeted rather than exploratory

## Key Insights

### Precision vs. Approximation
The difference between professional and amateur results often comes down to measurement precision. Visual estimation by AI consistently fails at professional standards.

### Configuration as Foundation
Many implementation failures stem from foundational configuration issues rather than coding skill. Fix the foundation first.

### Iterative Refinement
Even with precise specifications, expect 1-2 rounds of targeted refinement based on visual comparison to reference.

### Communication Quality
Clear, direct communication about specific problems leads to faster resolution than general descriptions or politeness that obscures issues.

## Recommended Workflow

1. **Setup Phase**: Verify all configurations work correctly
2. **Measurement Phase**: Get exact dimensions and specifications
3. **Implementation Phase**: Build with precise values incrementally
4. **Verification Phase**: Compare directly to reference design
5. **Refinement Phase**: Make targeted adjustments based on measurement
6. **Documentation Phase**: Commit changes with descriptive messages

This methodology transforms unreliable "close enough" results into reproducible, professional-quality implementations.