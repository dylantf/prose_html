# Getting started

ProseHtml is an Elm-style HTML builder for Saga. It gives you a small tree
type, helpers for conforming HTML elements and common attributes, safe text
escaping by default, and an explicit escape hatch for raw HTML.

## Basic usage

```saga
module Main

import ProseHtml as Html

page =
  Html.document [Html.lang "en"] [
    Html.head_ [] [
      Html.meta [Html.charset "utf-8"],
      Html.title_ [] [Html.text "ProseHtml"],
    ],
    Html.body [] [
      Html.main_ [Html.class "content", Html.data_ "controller" "page"] [
        Html.h1 [] [Html.text "Composable HTML"],
        Html.p [] [
          Html.text "Text is escaped, so <script> stays text.",
        ],
      ],
    ],
  ]

html_text = Html.render page
```

Element helpers return `HtmlNode`, so ordinary Saga functions are enough to
compose reusable views:

```saga
fun layout : String -> List Html.HtmlNode -> Html.HtmlNode
layout page_title children =
  Html.document [Html.lang "en"] [
    Html.head_ [] [Html.title_ [] [Html.text page_title]],
    Html.body [] children,
  ]
```

## Attributes

Use the named helpers for regular HTML attributes:

```saga
Html.a [
  Html.href "/docs",
  Html.class "nav-link",
  Html.aria "current" "page",
] [Html.text "Docs"]
```

Use `classes` or `class_names` to join class lists. Blank strings are ignored,
which makes conditional classes straightforward:

```saga
Html.button [
  Html.classes [
    "button",
    Html.class_if is_primary "button-primary",
    Html.class_if is_disabled "button-disabled",
  ],
] [Html.text "Save"]
```

Use `data_` for `data-*` attributes:

```saga
Html.div [
  Html.data_ "controller" "tabs",
  Html.data_ "active-tab" "overview",
] []
```

Use `attr` when a custom, experimental, or library-specific attribute is not
worth a first-class helper:

```saga
Html.div [Html.attr "hx-get" "/updates"] []
```

Duplicate attributes use the final value, which keeps composition predictable.
Boolean attributes render by presence:

```saga
Html.input [Html.disabled, Html.attr "disabled" "false"]
# <input disabled="false">
```

## Safety

`text` escapes HTML-sensitive characters. `unsafe_html` writes a string
verbatim and should only be used for content that is already trusted or
sanitized.

```saga
Html.div [] [
  Html.text "<strong>escaped</strong>",
  Html.unsafe_html "<strong>raw</strong>",
]
```

## Tags

ProseHtml includes helpers for the conforming HTML element set from the HTML
Living Standard, including void elements like `img`, `input`, `meta`, `source`,
`track`, and `wbr`. Helpers use the literal tag name where possible. A few names
use a suffix to avoid collisions with attributes or common Saga entrypoints:
`head_`, `main_`, `map_`, `title_`, `style_`, `data_el`, `object_`, `slot_el`,
`u_`, and `var_`.
