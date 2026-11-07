---
name: premium-ui-ux-design
description: Design, build, and polish modern web apps and mini-programs with consistent visual systems, meaningful micro-interactions, responsive layouts, accessible motion, and reliable functionality. Use when creating a new app, improving an existing interface, implementing interaction patterns, or reviewing UI quality.
---

# Premium UI/UX Design Skill

## Purpose

Use this skill to make AI-generated apps and mini-programs feel like professionally designed products. Prioritize functionality, usability, visual consistency, interaction quality, accessibility, and performance—in that order.

Do not add animation merely for decoration. Every interaction should help users understand what happened, what the system is doing, or what they can do next.

## 1. Six Useful Interaction Patterns

Choose patterns that fit the product. Do not force all six into every screen.

### 1.1 Completion Feedback

Give users clear feedback when they activate an action.

Requirements:
- Show a loading state when an operation is in progress.
- On success, transition smoothly to a success state, such as a checkmark and a short confirmation label.
- On failure, show a clear error state and allow retry where appropriate.
- Prevent accidental repeated submissions while an operation is pending.
- Keep the feedback connected to the real operation result; do not show success before the operation succeeds.
- Avoid abrupt layout shifts, flashing, or distracting effects.

Good use cases: form submission, saving settings, completing tasks, and payment confirmation.

### 1.2 Checkbox-Driven UI Updates

When a user checks or unchecks an item, update related interface elements from the same application state.

Requirements:
- Update completed-item counts immediately.
- Animate progress indicators smoothly.
- Update related buttons, labels, and summaries when relevant.
- Show a completion message when all required items are complete.
- Restore the correct state when the user returns or refreshes, if the application has persistence.
- Ensure displayed progress reflects actual data, not animation alone.

Good use cases: to-do lists, shopping lists, study plans, and settings.

### 1.3 Stacked Card Expansion

Present multiple cards in a compact stack and let the user expand one card to see its details.

Requirements:
- Make the selected card expand smoothly.
- Reposition or collapse surrounding cards to prevent unwanted overlap.
- Show the expanded card's full content and relevant actions.
- Provide an obvious way to close or collapse it.
- If appropriate, allow only one card to remain expanded at a time.
- Use natural spring-like motion without causing content clipping or layout jumps.
- Support touch and pointer interaction.

Good use cases: profiles, travel itineraries, course lists, and dashboards.

### 1.4 Draggable Snap Cards and Connecting Lines

Allow users to move cards or nodes and snap them to valid positions.

Requirements:
- Support dragging with touch and mouse or pointer input.
- Make the dragged item follow the pointer naturally.
- Snap the item to the nearest valid position when released.
- Update connecting lines continuously as connected items move.
- Prevent unintended overlap where the layout requires separation.
- Keep drag, snap, and connection logic stable and predictable.
- Avoid adding a large dependency for a small interaction unless it is justified.

Good use cases: flowcharts, mind maps, task boards, and node editors.

### 1.5 Inertial Wheel Picker

Create a wheel-style selector with natural momentum and clear selection feedback.

Requirements:
- Allow vertical touch scrolling.
- Apply momentum after the user releases the wheel, then gradually decelerate.
- Snap to the nearest option when scrolling stops.
- Make the selected option visually distinct.
- Allow direct selection by tapping or clicking an option.
- Support touch and appropriate desktop input.
- Respect boundaries unless looping is explicitly required.
- Keep the selected value synchronized with the application's real data.

Good use cases: dates, times, ages, quantities, and amounts.

### 1.6 Circular Reveal Transition

Use a circular expansion to reveal a new view when it improves the navigation experience.

Requirements:
- Start the reveal near the user's activation point when practical.
- Expand smoothly to reveal the destination view.
- Support a reverse transition when appropriate.
- Keep the existing routing and navigation behavior intact.
- Avoid blank screens, flashing, or visible rendering glitches.
- Consider a duration around 300–500 ms, adjusting to the context and platform.
- Respect reduced-motion preferences and provide a simpler alternative.

Good use cases: entering a detail view, changing themes, or opening an immersive screen.

## 2. Reusable Implementation Prompts

Use these prompts with coding agents such as ChatGPT, Codex, Cursor, Claude Code, Lovable, or Bolt. Adapt them to the project's framework and existing architecture. Implement and test one interaction at a time rather than changing everything at once.

### Prompt 1 — Completion Feedback Button

> Improve the button interactions in the current app by implementing polished completion feedback.
>
> Requirements:
> 1. Show a loading state immediately after the user activates the button.
> 2. After the operation succeeds, smoothly transition the button into a success state with a checkmark animation.
> 3. Change the button label to an appropriate confirmation, such as “Completed” or “Saved”.
> 4. If the operation fails, show a clear error state and allow the user to retry.
> 5. Keep the animation smooth, with no sudden jumps or page flashing.
> 6. Prevent repeated clicks from causing duplicate submissions.
> 7. Preserve the existing business logic and button functionality.
>
> Inspect the existing implementation first. Modify the code and verify that all states work correctly. Do not display success until the underlying operation has actually succeeded.

### Prompt 2 — Checkbox-Driven UI

> Add dynamic, state-driven interactions to the checkboxes in the current app.
>
> Requirements:
> 1. Update related UI whenever an item is checked or unchecked.
> 2. Update the completed-item count in real time.
> 3. Animate the progress bar smoothly based on the actual completion count.
> 4. When all required tasks are complete, show a concise completion message and a subtle animation.
> 5. Otherwise, display the current progress.
> 6. Keep the UI synchronized with real application data; do not implement visual-only changes.
> 7. Restore the correct state after refresh or when returning to the page, if the project already has a persistence mechanism.
>
> Keep the interface simple and verify that it works on mobile and desktop.

### Prompt 3 — Stacked Card Expansion

> Implement a Stacked Card Expansion interaction in the current app.
>
> Requirements:
> 1. Display multiple cards in a compact stacked layout.
> 2. Smoothly expand a card when the user selects it.
> 3. Reposition surrounding cards during expansion.
> 4. Show the selected card's full content and relevant action buttons.
> 5. Allow the card to collapse through a close control or by selecting it again.
> 6. Allow only one card to be expanded at a time unless the product requirements specify otherwise.
> 7. Use natural spring-like animation.
> 8. Support touch and mouse or pointer interaction.
>
> Prevent unwanted overlap, content clipping, and layout jumps. Preserve existing content and functionality.

### Prompt 4 — Draggable Snap Cards and Dynamic Connecting Lines

> Implement Draggable Snap Cards with Dynamic Connecting Lines in the current app.
>
> Requirements:
> 1. Allow users to drag cards freely within the permitted area.
> 2. Snap cards to valid target positions when they are close enough.
> 3. Make dragging feel natural and responsive.
> 4. Draw connecting lines between related cards.
> 5. Update the lines continuously as cards move.
> 6. Prevent unintended card overlap where appropriate.
> 7. Support both mouse and touch input.
> 8. Smoothly move a released card to the nearest valid position.
> 9. Keep dragging, snapping, and connection behavior reliable.
>
> Use an implementation suitable for the current project's framework. Avoid introducing a large dependency unless it is necessary.

### Prompt 5 — Inertial Wheel Picker

> Implement a polished Inertial Wheel Picker in the current app.
>
> Requirements:
> 1. Let users scroll vertically through options.
> 2. After the user releases their finger, apply momentum based on scroll velocity.
> 3. Gradually decelerate and snap to the nearest option.
> 4. Clearly highlight the currently selected option.
> 5. Allow users to select an option directly by tapping or clicking it.
> 6. Support touch input and appropriate desktop scrolling.
> 7. Keep the animation smooth and avoid stuttering.
> 8. Handle the first and last options correctly; do not loop unless explicitly required.
> 9. Synchronize the selected value with the actual application data.
>
> Verify that the picker works across different screen sizes and input methods.

### Prompt 6 — Circular Reveal Transition

> Add a Circular Reveal Transition to the current app.
>
> Requirements:
> 1. When the user activates a button or control, begin a circular reveal near the activation point where practical.
> 2. Expand the circle smoothly until the destination view is revealed.
> 3. Reveal the new page content without abrupt changes.
> 4. Support a reverse circular transition where appropriate.
> 5. Aim for a duration of approximately 300–500 ms, adjusted to the experience.
> 6. Avoid blank screens, flashing, or rendering glitches.
> 7. Preserve the existing routing and navigation functionality.
> 8. Respect `prefers-reduced-motion` and provide a reduced-motion alternative.
>
> Prefer the animation tools already used by the project. Do not add unnecessary dependencies.

## 3. General UI/UX Design System

Apply these standards to new projects and existing app improvements.

### 3.1 Design Philosophy
- Create a modern, polished, professional application.
- Prioritize usability over unnecessary visual effects.
- Give clear feedback for every meaningful interaction.
- Keep the interface clean, intuitive, and consistent.
- Avoid generic, repetitive AI-generated layouts.

### 3.2 Visual Design
- Use a consistent color palette.
- Establish a clear typography hierarchy.
- Maintain consistent spacing, alignment, and sizing.
- Use cards, rounded corners, and subtle shadows where they support the design.
- Avoid excessive gradients, borders, shadows, and decorative elements.
- Maintain sufficient contrast and readability.
- Use icons consistently and only when they improve comprehension.

### 3.3 Interaction Design
- Use the six interaction patterns above only where they suit the product.
- Give interactive elements clear hover, pressed, focused, loading, success, error, and disabled states as appropriate.
- Ensure every clickable element has a meaningful response.
- Prevent accidental double submissions.
- Keep transitions smooth and purposeful.
- Provide appropriate empty, loading, and error states.
- Ensure UI state reflects real application state.

### 3.4 Animation Standards
- Prefer subtle, natural motion.
- Use spring-based motion for cards and draggable elements when appropriate.
- As a starting point, use around 150–300 ms for simple interactions.
- As a starting point, use around 300–500 ms for larger transitions.
- Adjust timing to the task; these are guidelines, not rigid rules.
- Avoid excessive bouncing, long delays, and distracting effects.
- Respect reduced-motion accessibility settings.

### 3.5 Responsive Design
- Support mobile phones, tablets, and desktop screens.
- Use responsive layouts and appropriate breakpoints.
- Make touch targets comfortable to use.
- Prevent text overflow, clipped content, and overlapping elements.
- Keep important actions easy to reach.
- Test both portrait and landscape layouts where relevant.

### 3.6 Technical Requirements
- Inspect the existing project structure and conventions before changing code.
- Identify the framework, styling approach, state management, routing, and animation libraries already in use.
- Reuse existing components and dependencies where practical.
- Preserve existing business logic and working features.
- Connect interactions to real application state and data.
- Avoid unnecessary dependencies and excessive abstraction.
- Handle edge cases, errors, and asynchronous operations.
- Ensure animations do not interfere with navigation, input, or accessibility.
- Keep code maintainable and consistent with the project.

## 4. Recommended AI Development Workflow

Follow this sequence when building or improving an application.

### Step 1 — Design
- Understand the target users, main tasks, and product requirements.
- Propose the information architecture and page structure.
- Establish the visual direction, components, and design tokens.
- Review the proposed layout before implementing complex interactions.

### Step 2 — Build
- Implement the core screens and functionality.
- Connect components to real data and application state.
- Preserve existing project conventions.
- Make the basic experience work before adding decorative motion.

### Step 3 — Polish
- Add suitable micro-interactions.
- Implement the relevant patterns from the six interaction examples.
- Refine spacing, typography, hierarchy, transitions, and responsive behavior.
- Keep motion purposeful and consistent.

### Step 4 — Test
- Test buttons, forms, navigation, and interactive components.
- Test success, loading, empty, and error states.
- Test touch, mouse, and keyboard interactions where relevant.
- Check multiple screen sizes.
- Check reduced-motion behavior.
- Fix console errors, visual glitches, and regressions.

## 5. Final Quality Checklist

Before considering the work complete, verify:

- [ ] All buttons and navigation controls work.
- [ ] Interactive states reflect real application data.
- [ ] Loading, success, and error feedback are correct.
- [ ] Animations are smooth and do not block essential tasks.
- [ ] Touch, pointer, and keyboard interactions work where applicable.
- [ ] Layouts work at supported screen sizes.
- [ ] Text is readable and does not overflow.
- [ ] Accessibility and reduced-motion behavior have been considered.
- [ ] There are no obvious console errors or broken routes.
- [ ] Existing functionality has not regressed.
- [ ] Unnecessary dependencies have not been introduced.

## 6. Final Instruction to the Coding Agent

Do not merely make the application look attractive.

Make it feel like a professionally designed and developed product, with a consistent visual language, meaningful interactions, smooth and accessible motion, responsive layouts, and reliable functionality.

Prioritize, in order:

1. Functionality
2. Usability
3. Visual consistency
4. Interaction quality
5. Accessibility
6. Performance

When working in an existing project, inspect before editing, make focused changes, and test the result. Explain any interaction that cannot be implemented reliably in the current framework or environment rather than pretending it works.
