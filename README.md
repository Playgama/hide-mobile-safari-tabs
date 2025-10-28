### This example demonstrates a way to hide browser tabs in landscape mode on iOS.

**How it works:**
- The script tracks changes in the size and position of visualViewport.
- If the viewport height plus its top offset (viewport.height + viewport.offsetTop) is less than the screen height (minus a small margin for Chrome on iOS), it means the tabs are open.
- When the tabs are open:
  - An overlay with a hint appears.
  - A large “spacer” block is added so the user can scroll down.
  - When the user scrolls and the tabs disappear, the page becomes locked.
