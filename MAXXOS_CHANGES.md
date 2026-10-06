<!--
  Copyright (C) 2026 MaxxOS. All rights reserved.
-->
# MaxxOS Clock UI (DeskClock redesign)

Changed files:
- res/layout/desk_clock.xml, res/layout-land/desk_clock.xml : gradient background, large title, floating pill bottom nav (icons only)
- res/values/styles.xml : 34sp bold title, pill active indicator style
- res/values/themes.xml : nav bar colour blends with gradient
- res/color/tab_tint_color.xml : selected / unselected tab tint
- res/drawable/alarm_background.xml : glass rounded cards (alarm, world clock, timer)

New files:
- res/values/maxxos_colors.xml, res/values/maxxos_dimens.xml
- res/drawable/maxxos_bg_gradient.xml, res/drawable/maxxos_nav_pill.xml

Every changed/new file carries the "Copyright (C) 2026 MaxxOS" header.
Original AOSP/Apache notices are kept as required by the licence.
Java code and Android.bp are untouched.

World Clock (iOS style): res/layout/world_clock_city_container.xml (offset label above city name),
res/layout/world_clock_item.xml (row padding), res/values/styles.xml (MaxxOSWorldClock* text styles, 42sp time).

CI: .github/workflows/build-apk.yml builds a debug APK (package com.android.deskclock.dev) via Gradle.

Bottom row (portrait): main round button (plus / world / start-pause) now sits beside the floating pill nav.
Secondary round buttons (lap / reset / add) float just above that row, right side.
res/layout/desk_clock.xml, res/values/maxxos_dimens.xml; status bar colour matches gradient (res/values/themes.xml).
Landscape layout keeps the old side button column.

iOS World Clock look: res/layout/world_clock_item.xml (flat rows + hairline divider), res/values/maxxos_strings.xml,
src/com/android/deskclock/ClockFragment.java (offset label like "Today, +9HRS" / "Tomorrow, +16HRS").
Nav pill now uses theme (dynamic) colours; selected tab shows its label (MaxxDolby style).

Nav pill: translucent glass look (res/drawable/maxxos_nav_pill.xml, maxxos_colors.xml).

Liquid glass nav: src/com/android/deskclock/widget/MaxxOSLiquidNavigationView.java (new) used in
res/layout/desk_clock.xml and res/layout-land/desk_clock.xml. Glass bubble stretches between tabs,
lens-magnifies the icon/label inside, grows on press, and follows a dragging finger.
