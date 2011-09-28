## New UI To Do List

### Priority
* Archive.VG API inclusion
    * Get releases and tosec from Archive.VG response
    * Add fetched info to database (in OEDBGame gameWithArchiveDictionary:inDatabase:)
    * Add support for session dependent api stuff
* (done) Implement Screen Flow UI - https://github.com/mattball/MBCoverFlowView ? 
* Cores Preference pane
    * Decide if we want it
    * Add stuff to OECorePlugin (like -(NSView*)coreSettingsView; or something)
* Fix UI for pop out window title bar not working
* (done) Fix Filters in preferences
* Fix OEMenu
    * Highlight menu item even if mouse was not released
    * Add menu separator        **Done.**
    * Correct sizing if menu has only 1 item        **Done.**
    * Move selection by Arrow-Keys **Done**
* Fix GridView
    * Shadow on top (when scrolling reaches end)        **Done.**
    * Multiple selection
    * Move selection by Arrow-Keys
    * Add drag and drop
    * Center title and ratings on items        **Done.**
    * Fix memory usage
    * Fix resize crash
* HUD controls bar
    * Create save games menu
    * Make "Save Current Game" work 
    * "Done" Button
    * Add "stop fullscreen" button state
    * Set audio volume (individually for each game)
* MainMenu
    * enable/disable items
    * Manage "Last Played" menu
* Move About Window / Plugin Loading / HID Support away from OEGameDocument, remove OEGameDocument

    * * _Are we sure we want to remove OEGameDocument? The document handling framework allows us to do all sorts of nice Mac App things for free, including recent documents, etc. I think its foolish to throw that out. Plus, you could integrate with "Versions" for save states, etc etc. -vade_
    * * _You're right, NSDocument has some nice features. We should stick to it but still move the stuff mentioned somewhere more appropriate. cyco_

* Fix OESearchFieldCell (it loses it's text attributes when pressing enter-key)
* Localization of console names/images (e.g. NES<->Famicom)
* Remember state of collections item (collapsed/expanded)
* Add functionality to Preferences -> Library Folder Change/Reset Buttons
* Available Libraries (adding OELibraryPlugin or using OESystemPlugin? or just hardcoded)

* Setup Assistant: 
* * Welcome to OpenEmu, get you started
* * Download cores
* * Set up your preferences, and bind controller info
* * Import some roms!

* Maybe setup assistant is video game themed, like you are building a character from an old RPG? I dunno. Just a lame idea. Blinky in a tux with an eye piece ? Who knows!

### Eventually
* Remove spurious linker and compiler warnings
* Remove ivars since we are now 64 bit clean

### Organization
* Put UI Mockups on Github.        **Done.**
* Organize code, remove unecessary files
* Replace copyright headers
* Agreed upon code guidelines?

## Emulators To Do List