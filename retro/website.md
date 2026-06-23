# Marketing Discovery Report

## 1. Best Human Description

Retro Game Guides turns old plain-text video game walkthroughs into a readable, searchable, offline iPhone library.

* Best short tagline: Classic game guides, readable again.
* Best plain-English one-liner: Import or save TXT walkthroughs, make them readable on iPhone, jump to the section you need, and keep everything offline.
* Best App Store-style subtitle: Readable offline walkthroughs
* Best website hero headline: Stop fighting old TXT walkthroughs on your iPhone.
* Best website hero subheadline: Retro Game Guides reflows huge classic game guides, keeps the original layout when you need it, and turns your guides into a searchable offline library organized by game.

## 2. Product Promise

The core promise is: **make giant legacy TXT walkthroughs practical to use while you are actually playing.**

* What frustration does it remove?
  It removes the pain of opening huge fixed-width walkthroughs in Safari, Files, Notes, or a generic text app, then pinching, horizontal scrolling, losing your place, and searching through dense ASCII-era formatting.

* What does it help the user do faster or better?
  It helps the user read long walkthroughs comfortably, resume where they left off, search inside a guide, jump to generated or saved sections, and keep multiple guides organized under the right game.

* Why does it deserve to exist instead of Files, Safari, Notes, or a generic text reader?
  The app is guide-aware. It has a reflow engine for old TXT guide structure, preserves progress across layout modes, builds contents from guide patterns, stores per-guide sections and jumps, saves guides into a SQLite-backed game library, supports batch folder imports, and can save clean offline text snapshots from supported GameFAQs guide pages. Evidence spans [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:209>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1077>), [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>), and [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:41>).

## 3. Recommended Feature Hierarchy

### 1. Make old TXT guides readable on iPhone

* Human benefit: Huge old walkthroughs stop feeling like broken desktop files on a phone.
* Supporting technical features: Reflow, wrap, classic no-wrap, font size, proportional/monospace text, reader themes, per-guide layout preferences, progress preservation across layout changes.
* Evidence from code: [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:42>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:340>), [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:209>), [RGGuideTextTransformTests.swift](</Users/mettamatt/Sites/Retro Game Guides/Tests/RGGuideTextTransformTests/RGGuideTextTransformTests.swift:5>).
* Marketing priority: Hero / Primary.

### 2. Jump straight to the part you need

* Human benefit: The user can get back to the boss, puzzle, item, chapter, or checklist step without scrubbing through thousands of lines.
* Supporting technical features: Generated contents, user-created sections, recent jumps, in-guide search, snippets, line numbers, next/previous result navigation, recent searches.
* Evidence from code: [GuideSectionGenerator.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSectionGenerator.swift:4>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1298>), [GuideSearchIndex.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchIndex.swift:3>), [GuideSearchView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchView.swift:70>).
* Marketing priority: Primary.

### 3. Keep a real offline guide library

* Human benefit: A player with more than a few guides gets a clean collection instead of a pile of loose files.
* Supporting technical features: SQLite library, games with multiple guides, progress, favorites, recents, platform filtering, library search, source URL and attribution, per-guide sections/preferences/progress.
* Evidence from code: [LibraryModels.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryModels.swift:57>), [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:36>), [LibraryView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryView.swift:151>), [GameDetailView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameDetailView.swift:76>).
* Marketing priority: Primary.

### 4. Import collections without rebuilding them by hand

* Human benefit: Collectors can bring in a folder of TXT guides with a preview, duplicate checks, and diagnostics instead of importing one file at a time.
* Supporting technical features: Recursive TXT scanning, hidden-file skipping, catalog matching from path and filename signals, grouping by game, ready/review/duplicate/invalid states, SHA-256 content hash duplicate detection, platform-folder override and rescan flow.
* Evidence from code: [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:208>), [FolderGuideImportView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportView.swift:150>), [GuideMatcher.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideMatcher.swift:4>), [CatalogIndex.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/CatalogIndex.swift:48>).
* Marketing priority: Secondary, with one strong section for power users.

### 5. Find online, save offline

* Human benefit: A user can find a supported online guide, save a clean text copy, and read it later without relying on the website.
* Supporting technical features: GameFAQs URL allowlist, supported guide-page detection, controlled browsing, external-link handoff to Safari, HTML/preformatted text extraction, ephemeral download session, size and ZIP rejection, source URL storage, attribution.
* Evidence from code: [GameFAQsGuideURLDetector.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideURLDetector.swift:3>), [GameFAQsBrowserView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsBrowserView.swift:381>), [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:41>), [GameFAQsHTML.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsHTML.swift:26>).
* Marketing priority: Secondary / FAQ. Useful, but should not make the app sound like a generic downloader or browser.

### 6. Simple, private, offline-first ownership

* Human benefit: The user can keep a personal guide library on-device without accounts, ads, cloud sync, or a subscription.
* Supporting technical features: Local SQLite database, privacy manifest with no tracking and no collected data types, no account flow found, no ad SDK found, RevenueCat one-time unlock path, free 3-game limit.
* Evidence from code: [PrivacyInfo.xcprivacy](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/PrivacyInfo.xcprivacy:5>), [LibraryAccessPolicy.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryAccessPolicy.swift:4>), [UnlimitedLibraryPaywallView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/UnlimitedLibraryPaywallView.swift:95>), [docs/privacy-policy.html](</Users/mettamatt/Sites/Retro Game Guides/docs/privacy-policy.html:152>).
* Marketing priority: Trust / Pricing / FAQ, not the main hero.

## 4. Confirmed User-Facing Features

### Feature: Reflowed guide reading

* What the user can do: Turn hard-wrapped old TXT guide prose into more natural phone-width reading.
* Why it matters: The core pain is readability on a small screen.
* Suggested marketing phrasing: “Reflow long old walkthroughs into a phone-friendly reading view.”
* Evidence from code: [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:371>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1192>).
* Confidence: High.

### Feature: Classic no-wrap layout

* What the user can do: Keep the original fixed-width TXT layout when ASCII maps, tables, or formatting matter.
* Why it matters: Some old guides need their original structure.
* Suggested marketing phrasing: “Switch back to the classic layout whenever spacing matters.”
* Evidence from code: [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:1429>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2200>).
* Confidence: High.

### Feature: Wrap mode

* What the user can do: Wrap existing lines without full paragraph reflow.
* Why it matters: It gives a middle ground between exact layout and fully reflowed prose.
* Suggested marketing phrasing: “Choose reflow, wrap, or classic no-wrap reading.”
* Evidence from code: [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:42>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2200>).
* Confidence: High.

### Feature: Reader appearance controls

* What the user can do: Change font size, proportional/monospace style, and reader color theme.
* Why it matters: Long guide reading needs comfort, not just file opening.
* Suggested marketing phrasing: “Tune the reader for long sessions.”
* Evidence from code: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2050>).
* Confidence: High.

### Feature: Per-guide reader settings

* What the user can do: Keep guide-specific layout choices for monospace, wrapping, and reflow.
* Why it matters: Different guides need different layouts.
* Suggested marketing phrasing: “The app remembers the layout that works for each guide.”
* Evidence from code: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:340>), [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>).
* Confidence: High.

### Feature: Progress preservation across layout modes

* What the user can do: Change layout without losing their place.
* Why it matters: Reflow is only useful if it does not break resume position.
* Suggested marketing phrasing: “Switch layouts without losing where you were.”
* Evidence from code: [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:4>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1192>), [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:920>).
* Confidence: High.

### Feature: Generated contents

* What the user can do: Open a contents sheet built from guide headings and TOC-like patterns.
* Why it matters: Long guides become jumpable.
* Suggested marketing phrasing: “Jump through long guides with automatically built contents.”
* Evidence from code: [GuideSectionGenerator.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSectionGenerator.swift:4>), [RGGuideTOCCoreTests.swift](</Users/mettamatt/Sites/Retro Game Guides/Tools/RGGuideTOC/Tests/RGGuideTOCCoreTests.swift:16>).
* Confidence: High.

### Feature: User-created sections

* What the user can do: Select text and save it as a custom section.
* Why it matters: The user can mark their own boss, puzzle, route, checklist, or farming spot.
* Suggested marketing phrasing: “Save your own jump points inside any guide.”
* Evidence from code: [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:713>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1362>).
* Confidence: High.

### Feature: Recent jumps

* What the user can do: Return to recently visited sections within a guide.
* Why it matters: Play sessions often bounce between a walkthrough, item list, map, and boss section.
* Suggested marketing phrasing: “Get back to the places you just used.”
* Evidence from code: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1298>), [LibraryModels.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryModels.swift:175>).
* Confidence: High.

### Feature: In-guide search with snippets and line numbers

* What the user can do: Search inside a guide, view result snippets, see line numbers, and move next/previous through matches.
* Why it matters: It turns a 300 KB walkthrough into something usable mid-game.
* Suggested marketing phrasing: “Search for the boss, item, spell, or puzzle clue and jump through matches.”
* Evidence from code: [GuideSearchIndex.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchIndex.swift:3>), [GuideSearchView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchView.swift:196>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:1973>).
* Confidence: High.

### Feature: Whitespace-normalized guide search

* What the user can do: Find text even when old guide formatting inserts odd spacing or line breaks.
* Why it matters: It is more forgiving than a literal text search.
* Suggested marketing phrasing: “Search old guides without fighting their spacing.”
* Evidence from code: [GuideSearchIndex.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchIndex.swift:40>).
* Confidence: High.

### Feature: Recent searches

* What the user can do: Reuse recent search terms per game.
* Why it matters: Players often search the same item, dungeon, or character repeatedly.
* Suggested marketing phrasing: “Keep recent searches close while you play.”
* Evidence from code: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:304>), [GuideSearchView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchView.swift:70>).
* Confidence: High.

### Feature: Offline game library

* What the user can do: Save games and guides into a local library, with multiple guides per game.
* Why it matters: This is a collection manager, not just a text viewer.
* Suggested marketing phrasing: “Keep every guide organized by game.”
* Evidence from code: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>), [LibraryModels.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryModels.swift:57>).
* Confidence: High.

### Feature: Favorites, recents, platform filtering, and progress

* What the user can do: Filter the library, favorite guides, see recent games, and resume progress.
* Why it matters: The library scales beyond a handful of files.
* Suggested marketing phrasing: “Find the guide you need again, not just the file you imported.”
* Evidence from code: [LibraryView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryView.swift:151>), [GameDetailView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameDetailView.swift:260>).
* Confidence: High.

### Feature: Batch folder import

* What the user can do: Pick a parent folder, preview matched TXT guides, select ready groups, skip duplicates, see diagnostics, and add platform-folder mappings before rescanning.
* Why it matters: It makes an existing collection realistic to import.
* Suggested marketing phrasing: “Preview a folder import before it touches your library.”
* Evidence from code: [FolderGuideImportLandingView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportLandingView.swift:23>), [FolderGuideImportView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportView.swift:150>), [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:355>).
* Confidence: High.

### Feature: Duplicate detection

* What the user can do: Avoid importing the same guide again.
* Why it matters: Batch import would be risky without this.
* Suggested marketing phrasing: “Skip guides you already saved.”
* Evidence from code: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1440>), [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:262>).
* Confidence: High.

### Feature: Online guide save for supported GameFAQs pages

* What the user can do: Browse supported GameFAQs guide pages from a selected game and save a clean offline text snapshot.
* Why it matters: The user does not have to manually download and move every guide file.
* Suggested marketing phrasing: “Find a supported guide online, save a clean text copy, and read it offline.”
* Evidence from code: [GameFAQsBrowserView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsBrowserView.swift:896>), [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:41>).
* Confidence: High.

### Feature: Single and multiple TXT file import

* What the user can do: Import one or more plain-text guide files into a game.
* Why it matters: It supports normal file-based workflows without requiring batch import.
* Suggested marketing phrasing: “Import TXT walkthroughs from Files.”
* Evidence from code: [GameDetailView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameDetailView.swift:50>), [AddGameFlowView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/AddGameFlowView.swift:301>), [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:7>).
* Confidence: High.

### Feature: Free game limit and one-time unlock

* What the user can do: Keep up to 3 games free, then unlock unlimited games with a one-time purchase.
* Why it matters: The pricing model is simple and not subscription-led.
* Suggested marketing phrasing: “Keep 3 games free. Unlock unlimited games with a one-time purchase.”
* Evidence from code: [LibraryAccessPolicy.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryAccessPolicy.swift:4>), [UnlimitedLibraryPaywallView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/UnlimitedLibraryPaywallView.swift:95>).
* Confidence: High, except final public price should be confirmed.

## 5. Features to Avoid Overclaiming

### Risky claim: “Manually resolve every ambiguous folder import.”

* Safer claim: “Preview what matched, see which files need review, add platform-folder hints, and rescan.”
* Why: The UI shows ready groups, review buckets, diagnostics, and folder mapping, but it does not expose a per-file candidate picker to manually resolve ambiguous matches.
* Evidence from code: [FolderGuideImportView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportView.swift:694>), [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:540>).

### Risky claim: “Browse and download guides from the web.”

* Safer claim: “Open supported GameFAQs guide pages and save clean text snapshots for offline reading.”
* Why: Browsing is host/path constrained; unsupported links open externally or are blocked.
* Evidence from code: [GameFAQsGuideURLDetector.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideURLDetector.swift:3>), [GameFAQsBrowserView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsBrowserView.swift:381>).

### Risky claim: “AI-generated contents.”

* Safer claim: “Automatically built contents from guide headings and TOC patterns.”
* Why: The implementation is deterministic/rule-based, not AI.
* Evidence from code: [GuideSectionGenerator.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSectionGenerator.swift:4>), [RGGuideTextPatterns.swift](</Users/mettamatt/Sites/Retro Game Guides/Sources/RGGuideTextPatterns/RGGuideTextPatterns.swift:1>).

### Risky claim: “Perfectly reformats every old guide.”

* Safer claim: “Reflows common walkthrough prose while preserving many old guide structures.”
* Why: The transformer has many preservation rules and tests, but old TXT guide formats vary widely.
* Evidence from code: [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:371>), [RGGuideTextTransformTests.swift](</Users/mettamatt/Sites/Retro Game Guides/Tests/RGGuideTextTransformTests/RGGuideTextTransformTests.swift:5>).

### Risky claim: “Unlimited guides for free.”

* Safer claim: “Keep up to 3 games free; the one-time unlock removes the game limit.”
* Why: The free limit is games, not guide files. The code does not impose a guide-per-game cap, but storage and app limits still exist.
* Evidence from code: [LibraryAccessPolicy.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryAccessPolicy.swift:4>), [docs/app-review-positioning.md](</Users/mettamatt/Sites/Retro Game Guides/docs/app-review-positioning.md:70>).

### Risky claim: “No third-party SDKs.”

* Safer claim: “No account, no ads, no tracking; purchases use the App Store purchase flow.”
* Why: RevenueCat is present for purchases, so “no third-party SDKs” would be inaccurate.
* Evidence from code: [PurchaseStore.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/PurchaseStore.swift:1>), [PrivacyInfo.xcprivacy](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/PrivacyInfo.xcprivacy:5>).

### Risky claim: “Fully offline app.”

* Safer claim: “Saved and imported guides are available offline; online browsing, cover art, and purchases use the network when needed.”
* Why: The library and reader are local, but GameFAQs browsing, downloads, cover art, and purchases are networked.
* Evidence from code: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>), [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:41>), [PurchaseStore.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/PurchaseStore.swift:101>).

### Risky claim: “Imports any TXT collection automatically.”

* Safer claim: “Works best with clean filenames and platform folders; unmatched files are shown before import.”
* Why: Batch matching uses folder path, filename, IDs, slugs, and catalog signals, not guide contents.
* Evidence from code: [FolderGuideImportLandingView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportLandingView.swift:23>), [GuidePathParser.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuidePathParser.swift:3>), [GuideMatcher.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideMatcher.swift:43>).

## 6. Differentiators

### Strong differentiators

* Claim: “A reader built specifically for old TXT walkthroughs.”
  Why users care: It solves the actual pain better than a generic text viewer.
  Evidence from code: [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:209>), [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:429>).
  Recommended placement: Hero and main reader section.

* Claim: “Jump through long guides instead of scrolling forever.”
  Why users care: It saves time mid-game.
  Evidence from code: [GuideSectionGenerator.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSectionGenerator.swift:4>), [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2244>), [GuideSearchIndex.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideSearchIndex.swift:64>).
  Recommended placement: Primary feature section.

* Claim: “A real guide library, not a file pile.”
  Why users care: It scales to many games and multiple guides per game.
  Evidence from code: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>), [GameDetailView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameDetailView.swift:76>).
  Recommended placement: Primary feature section.

* Claim: “Batch import for existing guide collections.”
  Why users care: It appeals strongly to collectors with folders of legacy guides.
  Evidence from code: [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:220>), [FolderGuideImportView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImportView.swift:247>).
  Recommended placement: Secondary feature section, possibly lower on the page.

* Claim: “Save supported online guides as clean offline text.”
  Why users care: It removes the manual download/move/open workflow.
  Evidence from code: [GameFAQsBrowserView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsBrowserView.swift:896>), [GameFAQsHTML.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsHTML.swift:26>).
  Recommended placement: Secondary section or FAQ.

### Useful but common features

* Claim: “Font size, themes, and reader controls.”
  Why users care: Comfort.
  Evidence from code: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2050>).
  Recommended placement: Support the reader section, not standalone.

* Claim: “Favorites and recents.”
  Why users care: Quick access.
  Evidence from code: [LibraryView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryView.swift:151>), [GameDetailView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameDetailView.swift:260>).
  Recommended placement: Library section.

* Claim: “Plain-text file import.”
  Why users care: Expected basic workflow.
  Evidence from code: [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:7>).
  Recommended placement: Import section or FAQ.

### Internal implementation strengths that support trust but should not lead marketing

* Claim: “Durable raw/display offset mapping.”
  Why users care: They do not lose progress when changing layouts.
  Evidence from code: [GuideTextTransform.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextTransform.swift:4>).
  Recommended placement: Translate into “switch layouts without losing your place.”

* Claim: “SQLite-backed local library.”
  Why users care: Fast, durable offline organization.
  Evidence from code: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>).
  Recommended placement: Trust/proof section.

* Claim: “Encoding handling, ZIP/binary rejection, null stripping, and size limits.”
  Why users care: Imports are safer and less brittle.
  Evidence from code: [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:7>), [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:135>).
  Recommended placement: FAQ/trust, not hero.

## 7. Trust and Proof Points

* Local database: The app stores games, guides, progress, sections, jumps, reader preferences, source URLs, and attribution in a local SQLite schema.
  User-friendly version: “Your saved guide library lives on your iPhone.”
  Evidence: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1743>).

* Security-scoped file handling: File and folder imports use security-scoped access for user-selected files.
  User-friendly version: “The app reads the files and folders you choose.”
  Evidence: [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:7>), [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:180>).

* Encoding handling: Imports try UTF-8, UTF-16, Windows CP1252, ISO Latin 1, and Mac OS Roman.
  User-friendly version: “Old TXT files are handled more carefully than a generic import.”
  Evidence: [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:71>).

* Binary, ZIP, and size rejection: Import/download code rejects ZIPs, null-byte binary files, and files over 10 MB.
  User-friendly version: “The app tries to keep bad or wrong files out of your library.”
  Evidence: [GuideTextImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GuideTextImport.swift:7>), [FolderGuideImport.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/FolderGuideImport.swift:491>), [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:135>).

* Duplicate detection: Batch imports check source URL, FAQ ID, and content hash.
  User-friendly version: “Skip guides you already saved.”
  Evidence: [LibraryDatabase.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryDatabase.swift:1440>).

* Controlled online saving: GameFAQs browsing and saving are restricted to supported pages, with ZIP rejection and external-link handoff.
  User-friendly version: “Online saving is focused and user-directed.”
  Evidence: [GameFAQsGuideURLDetector.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideURLDetector.swift:3>), [GameFAQsBrowserView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsBrowserView.swift:381>).

* Ephemeral download session: GameFAQs guide downloads use an ephemeral URLSession.
  User-friendly version: “Online guide saving avoids persistent browser-style session storage for downloads.”
  Evidence: [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:41>).

* Source attribution: Downloaded guides store source URL/site/attribution.
  User-friendly version: “Saved guides keep their source attached.”
  Evidence: [GameFAQsGuideDownload.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/GameFAQsGuideDownload.swift:89>), [LibraryModels.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryModels.swift:123>).

* Reflow and contents tests: The repo has tests for real guide patterns and large fixture anchors.
  User-friendly version: “The reader is tested against the weird formatting old walkthroughs actually use.”
  Evidence: [RGGuideTextTransformTests.swift](</Users/mettamatt/Sites/Retro Game Guides/Tests/RGGuideTextTransformTests/RGGuideTextTransformTests.swift:5>), [RGGuideTOCCoreTests.swift](</Users/mettamatt/Sites/Retro Game Guides/Tools/RGGuideTOC/Tests/RGGuideTOCCoreTests.swift:16>).

* Privacy posture: Privacy manifest declares no tracking and no collected data types; docs say no account, ads, analytics, cloud sync, or Retro Guides server.
  User-friendly version: “No account. No ads. No tracking.”
  Evidence: [PrivacyInfo.xcprivacy](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/PrivacyInfo.xcprivacy:5>), [docs/privacy-policy.html](</Users/mettamatt/Sites/Retro Game Guides/docs/privacy-policy.html:152>).
  Caveat: Purchases use RevenueCat, so avoid “no third-party SDKs.”

## 8. Existing Copy and Useful Phrases

### Copy worth reusing

* “An offline-first guide library and reader for classic game walkthroughs, built to make big plain-text guides easy to save, search, and actually read on iPhone.”
  Source: [docs/marketing.md](</Users/mettamatt/Sites/Retro Game Guides/docs/marketing.md:1>).

* “Find the section. Save your place. Keep it offline.”
  Source: [docs/marketing.md](</Users/mettamatt/Sites/Retro Game Guides/docs/marketing.md:1>).

* “A guide reader built for guides.”
  Source: [docs/marketing.md](</Users/mettamatt/Sites/Retro Game Guides/docs/marketing.md:1>).

* “Keep 3 games free. Unlock unlimited games with a one-time purchase.”
  Source: [LibraryAccessPolicy.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryAccessPolicy.swift:21>), [design/README.md](</Users/mettamatt/Sites/Retro Game Guides/design/README.md:145>).

* “Import one or more plain-text guide files.”
  Source: [ImportGuideView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ImportGuideView.swift:20>).

* “Find and save an online guide for offline reading.”
  Source: [AddGameFlowView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/AddGameFlowView.swift:259>).

* “Search in Guide,” “Contents,” “Reading Settings,” “Make Section,” “Recent Jumps,” and “Your Sections.”
  Source: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:591>), [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:713>).

### Copy that is accurate but too technical

* “Raw/display offset mapping.”
  Better marketing translation: “Switch layouts without losing your place.”

* “Matching uses folder path and filename, not TXT contents.”
  Better marketing translation: “Works best with clean filenames and platform folders.” Good for FAQ/import guidance, not the hero.

* “FTS5,” “content hash,” “sourceFAQId,” “display transform version.”
  Better marketing translation: “Fast library search,” “skip duplicates,” “keep source details,” and “remember your place.”

### Copy that should be rewritten

* “Review flow when something is ambiguous.”
  Better: “See which files need review, add platform hints, and rescan.” The current UI diagnoses ambiguity but does not manually resolve every file.

* “Batch import that scales.”
  Better: “Preview a folder before importing.” It is more concrete and less enterprise-sounding.

* “No analytics SDKs.”
  Better: “No account, no ads, no tracking.” Confirm final RevenueCat/privacy wording before publishing.

* Any copy that leads with GameFAQs as the product.
  Better: Lead with the reader and library; describe GameFAQs as a supported source for user-saved guide snapshots.

## 9. Landing Page Outline

### 1. Hero

* Section goal: State the main promise immediately.
* Suggested headline: Stop fighting old TXT walkthroughs on your iPhone.
* Suggested body copy: Retro Game Guides turns giant plain-text walkthroughs into a readable, searchable, offline library. Reflow old guides, keep the classic layout when spacing matters, and jump back to the exact section you need.
* Screenshot or visual needed: iPhone reader screenshot in reflow mode, ideally with the reading settings or contents affordance visible.
* Primary proof points: Reflow/wrap/no-wrap, offline library, search/jump.

### 2. Problem Section

* Section goal: Make the pain obvious.
* Suggested headline: Old walkthroughs were not made for phone screens.
* Suggested body copy: Classic TXT guides are huge, fixed-width, and packed with hand-made formatting. In a generic reader, you pinch, pan, search blindly, and lose your place.
* Screenshot or visual needed: Side-by-side visual of raw fixed-width text versus readable reflowed text.
* Primary proof points: No-wrap and reflow modes exist; progress survives mode changes.

### 3. Main Reader Feature Section

* Section goal: Prove the app solves the core reading problem.
* Suggested headline: Read the guide your way.
* Suggested body copy: Use reflow for long prose, wrap for a lighter touch, or classic no-wrap for maps, tables, and ASCII layouts. Adjust font size, text style, and color theme for long sessions.
* Screenshot or visual needed: Reading Settings sheet.
* Primary proof points: [ReaderView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderView.swift:2050>), [ReaderTextView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/ReaderTextView.swift:42>).

### 4. Navigation/Search Feature Section

* Section goal: Show that the app helps users find answers fast.
* Suggested headline: Jump to the boss, item, puzzle, or chapter.
* Suggested body copy: Open generated contents, save your own sections, revisit recent jumps, or search inside the guide with snippets, line numbers, and next/previous match navigation.
* Screenshot or visual needed: Contents sheet plus search results sheet.
* Primary proof points: Generated contents, custom sections, recent jumps, normalized search.

### 5. Library Feature Section

* Section goal: Position the app as a guide collection, not just a reader.
* Suggested headline: Build a real guide library.
* Suggested body copy: Keep multiple guides under each game, track reading progress, favorite important guides, filter by platform, and return to recent games.
* Screenshot or visual needed: Library screen and game detail screen.
* Primary proof points: SQLite library, games with multiple guides, progress, recents/favorites/platform filters.

### 6. Import Feature Section

* Section goal: Appeal to users with existing guide files.
* Suggested headline: Bring in your TXT guides without busywork.
* Suggested body copy: Import single guides from Files or preview a whole folder. The app scans TXT files, groups ready matches by game, skips duplicates, and shows diagnostics before import.
* Screenshot or visual needed: Folder import preview with ready count, grouped games, and diagnostics.
* Primary proof points: Recursive TXT scan, duplicate detection, grouped preview, platform-folder rescan.

### 7. Offline/Privacy/Trust Section

* Section goal: Build confidence.
* Suggested headline: Your guide library stays yours.
* Suggested body copy: Saved and imported guides live on your iPhone for offline reading. No account, no ads, no tracking, and no cloud library.
* Screenshot or visual needed: Small trust panel, not necessarily a screenshot.
* Primary proof points: Local SQLite, privacy manifest, privacy policy, no account flow found. Include caveat in internal copy that online guide saving, purchases, and cover art need network.

### 8. Pricing/Unlock Section

* Section goal: Explain monetization cleanly.
* Suggested headline: Start free. Unlock when your library grows.
* Suggested body copy: Keep up to 3 games free. A one-time purchase unlocks unlimited games. No subscription. No ads.
* Screenshot or visual needed: Paywall screenshot or simplified pricing block.
* Primary proof points: [LibraryAccessPolicy.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/LibraryAccessPolicy.swift:4>), [UnlimitedLibraryPaywallView.swift](</Users/mettamatt/Sites/Retro Game Guides/apple/RetroGuideReader/RetroGuideReader/UnlimitedLibraryPaywallView.swift:95>). Confirm public price before including it.

### 9. FAQ

* Section goal: Prevent overclaim confusion.
* Suggested headline: Questions before you import.
* Suggested body copy topics: Supported file types, how batch matching works, whether it works offline, what the free limit means, online guide saving, GameFAQs affiliation/source rights, privacy.
* Screenshot or visual needed: None.
* Primary proof points: Import limits, GameFAQs disclaimer, privacy policy.

### 10. Final CTA

* Section goal: Repeat the promise and send users to download.
* Suggested headline: Make your old walkthroughs usable again.
* Suggested body copy: Save your guides, search them fast, and keep them ready offline.
* Screenshot or visual needed: App icon plus App Store badge.
* Primary proof points: App Store URL: https://apps.apple.com/us/app/retro-guides/id6771456010

### 11. Footer/Legal Links

* Section goal: Handle trust/legal basics.
* Suggested content: Privacy Policy, Support, Terms if needed, App Store link, “Not affiliated with GameFAQs/GameSpot/Fandom” if legally required.
* Screenshot or visual needed: None.
* Primary proof points: Existing privacy policy at [docs/privacy-policy.html](</Users/mettamatt/Sites/Retro Game Guides/docs/privacy-policy.html:1>).

## 10. Screenshot Plan

### Screen/view to capture: Reader in reflow mode

* What it should demonstrate: A giant old walkthrough becoming readable on iPhone.
* Suggested caption: “Reflow old TXT guides for phone-friendly reading.”
* Essential or optional: Essential.

### Screen/view to capture: Reading Settings sheet

* What it should demonstrate: Reflow/wrap/no-wrap, font size, style, and color controls.
* Suggested caption: “Choose reflow, wrap, or classic layout.”
* Essential or optional: Essential.

### Screen/view to capture: Contents sheet

* What it should demonstrate: Generated contents, user sections, and recent jumps.
* Suggested caption: “Jump back to the section you need.”
* Essential or optional: Essential.

### Screen/view to capture: Search results sheet

* What it should demonstrate: Snippets, line numbers, recent searches, and search navigation.
* Suggested caption: “Search inside long guides with useful context.”
* Essential or optional: Essential.

### Screen/view to capture: Library screen

* What it should demonstrate: Games organized as a library with filters/search/recents/favorites.
* Suggested caption: “Keep guides organized by game.”
* Essential or optional: Essential.

### Screen/view to capture: Game detail screen

* What it should demonstrate: Multiple guides for one game, progress, favorites, and source labels.
* Suggested caption: “Save walkthroughs, FAQs, maps, and notes under one game.”
* Essential or optional: Essential.

### Screen/view to capture: Folder import preview

* What it should demonstrate: Ready count, games to import, selection, duplicates/diagnostics.
* Suggested caption: “Preview a folder import before adding anything.”
* Essential or optional: Essential.

### Screen/view to capture: Add game / guide source options

* What it should demonstrate: Add manually or search online.
* Suggested caption: “Import TXT files or save a supported online guide.”
* Essential or optional: Optional.

### Screen/view to capture: GameFAQs browser save flow

* What it should demonstrate: Supported guide page with save/download action.
* Suggested caption: “Save a clean offline text copy from supported guide pages.”
* Essential or optional: Optional; use carefully because the website should not look like a GameFAQs downloader first.

### Screen/view to capture: Paywall/unlock screen

* What it should demonstrate: 3 games free, one-time unlimited unlock, no subscription/no ads.
* Suggested caption: “Start free. Unlock unlimited games when your library grows.”
* Essential or optional: Essential if pricing appears on the page.

## 11. Positioning Options

### Option 1: Readability-first

* Positioning angle: Make old TXT walkthroughs readable on iPhone.
* Hero headline: Stop fighting old TXT walkthroughs on your iPhone.
* Hero subheadline: Reflow huge classic game guides, keep the original layout when spacing matters, and save your place in an offline guide library.
* Best audience: Any retro player who has opened a walkthrough on a phone and hated the experience.
* Pros: Clearest pain, broadest appeal, best supported by the code.
* Cons: Does not immediately show the depth of library/import features.
* Whether I recommend it: Yes. This should be the main direction.

### Option 2: Fast navigation/search-first

* Positioning angle: Jump straight to the exact answer.
* Hero headline: Find the part of the guide you need.
* Hero subheadline: Search with snippets and line numbers, jump through generated contents, and save your own sections for later.
* Best audience: Players actively using guides during gameplay.
* Pros: Very practical and benefit-led.
* Cons: Less emotionally distinct than the readability pain; depends on users already understanding the problem of long guides.
* Whether I recommend it: Use as the second major section, not the hero.

### Option 3: Offline library-first

* Positioning angle: Build a real offline library for classic game guides.
* Hero headline: Keep every classic game guide in one offline library.
* Hero subheadline: Organize multiple guides by game, track progress, favorite the important ones, and read without an account or cloud library.
* Best audience: Collectors and preservation-minded players.
* Pros: Differentiates from Safari and Files.
* Cons: Less urgent than the reading pain; “library” can sound administrative.
* Whether I recommend it: Strong secondary positioning.

### Option 4: Batch import-first

* Positioning angle: Bring an existing TXT guide collection into order.
* Hero headline: Turn your old guide folder into an iPhone library.
* Hero subheadline: Preview a folder import, group matched TXT files by game, skip duplicates, and see what needs review before importing.
* Best audience: Power users with large local guide collections.
* Pros: Distinctive and highly credible from the code.
* Cons: Too niche for the main audience; import matching caveats require careful wording.
* Whether I recommend it: Not as the main direction. Use lower on the page.

### Option 5: Privacy/offline simplicity-first

* Positioning angle: No account, no ads, no tracking, local offline guides.
* Hero headline: Your guides, saved locally. No account required.
* Hero subheadline: Import or save walkthroughs to your iPhone and read them offline without ads, tracking, or a cloud library.
* Best audience: Privacy-conscious users and people who dislike subscriptions/accounts.
* Pros: Trustworthy, simple, and supported by repo docs/manifests.
* Cons: Privacy is not the main problem the app solves; it is a reason to believe.
* Whether I recommend it: Use as a trust section and FAQ, not the hero.

## 12. Recommended Final Direction

The strongest positioning is **readability-first**:

**“Stop fighting old TXT walkthroughs on your iPhone.”**

That should lead because it names the normal human problem immediately. The code’s most impressive work is not just that it stores guides; it makes old guide text usable on a phone while preserving escape hatches for classic formatting. The reflow engine, layout modes, appearance controls, and progress mapping all support this promise.

The secondary story should be **fast navigation**: generated contents, user sections, recent jumps, and search with snippets/line numbers. This is the natural next benefit after readability: once the guide is readable, the user wants to get to the exact answer quickly.

The third story should be **offline library**: games, multiple guides, progress, favorites, recents, platform filters, source details, and per-guide state. This explains why the app is better than a one-off text reader.

Batch import should be a strong supporting section for collectors, but not the lead. It is valuable and differentiated, but the caveats around matching make it less clean as a hero promise.

Privacy, offline behavior, no account, no ads, and one-time unlock should be trust and pricing copy. They make the product feel respectful, but they are not the main reason someone needs it.

Do not emphasize the app as a GameFAQs downloader, an AI contents generator, or a universal text-file import machine. The accurate, persuasive story is simpler: **old walkthroughs become readable, searchable, jumpable, and organized offline.**

## 13. Questions Before Building

* What is the exact public app name: “Retro Game Guides,” “Retro Guides,” or something else? The name under the app icon will be “Retro Guides”
* What is the App Store URL or launch-state CTA: download now, join TestFlight, coming soon, or notify me? Download now: https://apps.apple.com/us/app/retro-guides/id6771456010
* What is the final public price, and should the website show the price or just say “one-time purchase”? $4.99 but the price will vary by region. 
* Is the final approved privacy wording “no analytics,” “no tracking,” or “no ad/tracking analytics,” given RevenueCat is used for purchases? RevenueCat is used for payment not for tracking. 
* What support/contact URL or email should the site link to? mavatar@gmail.com (that is in the code already)
* Should the website mention GameFAQs by name, or use source-neutral copy and reserve GameFAQs details for FAQ/legal context? Better to use source-neutral copy. 
* What not-affiliated/legal language is required for GameFAQs/GameSpot/Fandom and game cover art?
* Which screenshots are approved to use, and should they show real guides, sample/demo text, or public-domain/synthetic guide content? We ship with a sample guide so we will use that. 
* Should the marketing site use the existing design system directly, or adapt it into a lighter public-facing web style? The website should have a similar look and feel but not need to be exact because the design system was built for iOS and not the web. 
