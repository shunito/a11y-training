# Comparison between Bad and Good Button Implementations

## 1. Bad Example: `src/components/examples/button/Koku.tsx`

### Code Characteristics
- Implemented using a `div` element with an `onClick` handler.
- Does not use semantic HTML elements like `button` or `a`.

### Accessibility Issues
1. **Keyboard Inaccessibility**
   - The `div` element is not focusable by default. Users navigating with a keyboard (using Tab key) cannot reach this element.
      - Pressing Enter or Space keys on this element does not trigger the click event.
         - Keyboard-only users and screen reader users cannot interact with this button.
         2. **Missing Semantics**
            - Screen readers will announce this element as a plain text or group, not as a "button".
               - Visually impaired users will not know that this element is interactive.

               ---

               ## 2. Good Example: `src/components/examples/button/ButtonElement.tsx`

               ### Code Characteristics
               - Implemented using the standard HTML `<button>` element.
               - Passes `onClick` and `children` props properly.

               ### Accessibility Improvements
               1. **Native Keyboard Support**
                  - The `<button>` element is automatically focusable and included in the tab order.
                     - Pressing Enter or Space keys automatically triggers the `onClick` event handler.
                     2. **Correct Semantics**
                        - Screen readers will correctly announce this element as a "button" (or equivalent depending on the language settings).
                           - This provides clear guidance to screen reader users that this is an interactive action element.
                           
