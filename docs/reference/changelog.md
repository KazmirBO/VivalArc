## 🗓️ 2026.06.10 | v2.0.0
Ground-up rewrite of the stylesheet. Selector behavior is intentionally identical to v1.4.0 — what changed is structure, shadows, and motion.

1. Rewritten with native CSS nesting: shared guards such as `#browser:not(.tabs-top, .tabs-bottom)` are now declared once per section instead of being repeated on almost every rule, which makes the file easier to scan and cheaper for the style engine to match.
2. Consolidated duplicate rules with `:is()`, merged the two `:has()` probes for tiled/mosaic page grids into one each, and removed a redundant `theme-light` shadow rule (the fallback already covered it).
3. New layered webview shadows for both light and dark themes — a tight contact shadow, a soft ambient shadow, and a hairline edge.
4. Snappier motion: a decelerated `cubic-bezier(0.2, 0, 0, 1)` easing token replaces plain `ease`, plus gentle hover transitions on toolbar buttons and the address field (all gated behind `prefers-reduced-motion: no-preference`).
5. New accent-colored focus ring on the address/search field (`--urlbar-focus-ring`), derived from the active theme via `color-mix()`.
6. Deliberately no `@layer`: layered rules would lose the cascade against Vivaldi's own unlayered styles.

## 🗓️ 2026.05.21 | v1.4.0
Updated for Vivaldi 8.0, which introduced the "Unified frame" UI overhaul and a tabs management backend rewrite.

1. Updated compatibility for Vivaldi 8.0.
2. Added `[v8.0 check]` markers in the stylesheet at selectors most likely to be affected by the Unified frame — inspect the live DOM at `vivaldi://inspect/#apps/` if anything looks off.
3. Merged the auto-hiding tab bar feature (originally a separate `autotab` variant by @Zettry) into the root stylesheet as an optional toggle: set `--enable-autohide-tabbar: 1` in the `:root` block to enable it.
4. Added smooth transition animation for the tab bar (`--tabbar-transition`) and panel container.
5. Added `--window-button-hover-opacity` variable for configurable window button hover opacity.
6. Moved legacy variants (`autotab`, `compact`) to `archive/v7.7/` — they are no longer maintained as separate files.

## 🗓️ 2026.03.26 | v1.3.0
This update targets the latest Vivaldi 7.9 release and refreshes VivalArc after a long gap between updates.

1. Updated compatibility for Vivaldi 7.9.
2. Simplified the stylesheet again and removed more custom overrides, so the root version is less fragile against future Vivaldi UI changes.
3. After more than a year without updates, several visual issues that had accumulated over time were cleaned up in this release.

Today, most mainstream browsers, including Chrome, already offer built-in vertical tabs. For me, Vivaldi's remaining advantage is still its level of customization. Because of that, I plan to keep maintaining VivalArc, but future updates will focus more on fixing visual regressions and interface bugs than on adding more stylistic branches.

## 🗓️ 2024.11.03 | v1.1.0
Vivaldi recently updated to version 7.0, bringing noticeable UI changes—more refined icons, a modernized look, and enhanced shadows on selected sidebar tabs. This update is highly recommended as it makes VivalArc look even better.

Thankfully, this major update didn’t cause any issues with VivalArc. However, a few accumulated GitHub issues were addressed:

1. Footer visibility issue: The footer is now visible by default, but you can still hide it in settings. [#28](https://github.com/tovifun/VivalArc/issues/28) @IamMiao
2.	Added draggable functionality to the popup page’s address bar, suggested by @Zettry. [#30](https://github.com/tovifun/VivalArc/issues/30)
3.	Restored the scrollbar in the tab bar to allow width adjustments, though it slightly impacts aesthetics. [#31](https://github.com/tovifun/VivalArc/issues/31)
4.	Added an auto-hiding tab bar feature (suggested by @Zettry), introduced as a separate variant at the time. [#21](https://github.com/tovifun/VivalArc/issues/21) [#29](https://github.com/tovifun/VivalArc/issues/29)

## 🗓️ 2024.08.17 | v1.0.4
### 1. Optimization for Vivaldi 6.9
Vivaldi Snapshot 6.9 (the Beta version of Vivaldi) was recently updated, which introduced a minor issue with VivalArc—an extra semi-transparent layer appeared on the sidebar background #24 . This update primarily addresses and resolves this issue.

### 2. How to Use Different Versions of VivalArc
Some users asked how to use the style with a title bar #26. At that time, I created several VivalArc variants for different preferences. For historical notes, please refer to: [Legacy Variant Notes](../guides/variants-guide.md).

### 3. Reflect New Tab Theme
I recently discovered a plugin called [Reflect New Tab](https://chromewebstore.google.com/detail/reflect-new-tab/jnhdkfampckckkmbanadkkjlcaemdkob), which features a beautiful gradient background. I decided to create a [Vivaldi theme](./curated-themes.md) using this background, and the results were impressive—it gave VivalArc a whole new look. My personal favorite is the pink theme, and I highly recommend you give it a try.

## 🗓️ 2024.06.29 | v1.0.3
1. This version mainly addresses a minor issue in Vivaldi 6.8 update—[Issue#20](https://github.com/tovifun/VivalArc/issues/20). (Special thanks to @NextEcho for providing CSS solutions, although I did not entirely adopt their method in the end).
2. In previous versions, I created a few gradient Vivaldi themes to mimic the Arc style and included them in the project files for everyone to use. A few days ago, I explored the Themes section on the Vivaldi Community and discovered many suitable themes. I realized there was no need to go out of my way to create new themes, so I tried some of the popular themes in the Community and selected a few that I found fitting. Here’s how you can use them:
	1.	Open the [recommended theme link](./curated-themes.md).
	2.	Click on the theme name to go to its page.
	3.	Click the install button below the theme.

## 🗓️ 2024.05.12 | v1.0.2
- The latest version of VivalArc primarily focuses on optimizing two aspects of Vivaldi 6.7：
  - The window buttons in the top-left corner of macOS can no longer be customized, causing them to overlapping the elements of the TabBar
  - The 'Add Button' for creating new tabs has been relocated to the bottom of the window

## 🗓️ 2024.03.30
- Optimized the height of the title bar

## 🗓️ 2023.11.09
- Increase the gap on both sides of the Tabbar.
- The Tabbar is now draggable by default (if you don't want it to be draggable, you can change `.tabbar-wrapper` to `no-drag` in file `main_arc.css`.)
- The pop-up settings page now has a proper title bar (in previous versions, the close button was very small).
- Two new themes added, `theme-gradientGreenLight` and `theme-gradientPinkLight`.
- One thing I still want to modify is the Tabbar, it's still a bit rough at the moment, and it should be specifically optimized in future versions.

## 🗓️ 2023.09.17
- This update includes many changes. I have reviewed every line of code to make the styles more refined.
- The main updates are as follows:
  - The shadows on the webview areas have been made more subtle.
  - Panel optimization for more consistent styles across various configurations.
  - Uniform colors for the Tabbar and Menubar.
- For those who want to customize more, I was planning to create a video demonstration, but the video isn't ready yet. You can follow my [Youtube](https://www.youtube.com/channel/UCbmcO7HxXDYqEZFb-QgmRsw) for updates. Once the demo video is ready, I will post it there. For now, you can open `css/main.css` to make some additional configurations. Here are some brief instructions:
  - `--window-border` allows you to set the thickness of the border around the window. I recommend setting it between 4px and 16px. (Setting it to 0 means no border.)
  - `--window-button-opacity` lets you adjust the opacity of the three buttons in the top right corner for Windows users. I've set it to 0.3 by default. You can set it any num between 0 and 1. Higher values make the buttons more visible. If set to around 0.1, they become almost invisible but still appear on mouse hover. If you want a cleaner header, you can set it below 0.1.
  - If you find the drag area for the top header too small, you can increase the `--window-header` value, or you can use the following method:
  - Change the `webkit-app-region` of `tabbar-wrapper` from `nodrag` to `drag` to make the entire tabbar draggable. However, some users have reported that dragging in this area may affect the left-side panel (the right-side panel should be less problematic, as I have set it to the right myself). If you encounter any issues during testing, please provide feedback.
  - Please note that if you make the tabbar area draggable, the double-click to create a new tab feature in the tabbar area will be disabled. You can comment out the "display new tab button" above to add a new tab button to the tabbar area.
- **Note: After making CSS modifications, you will need to restart your browser for the changes to take effect.**

 ![Annotation](../installation/images/annotate-config.png)


## 🗓️ 2023.07.23 
- Several users on Windows reported that they couldn't see the three window buttons, which was very awkward, so I added them back this time.
- The three buttons in the upper-left corner of the Mac are also added back, but for the sake of aesthetics, they are grayed out, and only colored when the mouse hovers over them.

## 🗓️ 2023.03.12
- Optimization
    - Hide the border around the window when in full screen mode;
    - Show the title bar and keep the three buttons in the upper-left corner visible (many users had trouble finding them);
    - Remove drag-and-drop for the Tab bar (it caused many unexpected bugs);
    - Simplify the style sheet
        - Previously, too many custom CSS styles were used to make the appearanc