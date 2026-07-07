---
title: ProseHtml
---

## Types

### HtmlNode

```saga
type HtmlNode =
  | Doctype
  | Text String
  | UnsafeHtml String
  | Element String (List HtmlAttr) (List HtmlNode)
  | VoidElement String (List HtmlAttr)
  | Fragment (List HtmlNode)
```

A composable HTML tree.

### HtmlAttr

```saga
type HtmlAttr =
  | Attr String String
  | BoolAttr String
```

An HTML attribute. Boolean attributes render without a value.

## Functions

### text

```saga
fun text : String -> HtmlNode
```

Escapes text and renders it as an HTML text node.

### unsafe_html

```saga
fun unsafe_html : String -> HtmlNode
```

Renders an already-safe HTML string without escaping.

### fragment

```saga
fun fragment : List HtmlNode -> HtmlNode
```

Groups several nodes without adding a wrapper element.

### element

```saga
fun element : String -> List HtmlAttr -> List HtmlNode -> HtmlNode
```

Creates a normal element with attributes and children.

### void_element

```saga
fun void_element : String -> List HtmlAttr -> HtmlNode
```

Creates a void element with attributes and no children.

### attr

```saga
fun attr : String -> String -> HtmlAttr
```

Creates a string-valued attribute.

### bool_attr

```saga
fun bool_attr : String -> HtmlAttr
```

Creates a boolean attribute.

### int_attr

```saga
fun int_attr : String -> Int -> HtmlAttr
```

Creates an integer-valued attribute.

### bool_value_attr

```saga
fun bool_value_attr : String -> Bool -> HtmlAttr
```

Creates an attribute whose value is either "true" or "false".

### doctype

```saga
fun doctype : HtmlNode
```

Renders the HTML5 doctype.

### document

```saga
fun document : List HtmlAttr -> List HtmlNode -> HtmlNode
```

Creates a complete HTML document with an HTML5 doctype.

### render

```saga
fun render : HtmlNode -> String
```

Renders HTML to a string.

### id

```saga
fun id : String -> HtmlAttr
```

### class

```saga
fun class : String -> HtmlAttr
```

### class_names

```saga
fun class_names : List String -> HtmlAttr
```

Joins non-blank class names into a class attribute.

### classes

```saga
fun classes : List String -> HtmlAttr
```

Alias for class_names.

### class_if

```saga
fun class_if : Bool -> String -> String
```

Returns a class name when the condition is true, or an empty string otherwise.

### accesskey

```saga
fun accesskey : String -> HtmlAttr
```

### autocapitalize

```saga
fun autocapitalize : String -> HtmlAttr
```

### autocorrect

```saga
fun autocorrect : String -> HtmlAttr
```

### contenteditable

```saga
fun contenteditable : Bool -> HtmlAttr
```

### dir

```saga
fun dir : String -> HtmlAttr
```

### draggable

```saga
fun draggable : Bool -> HtmlAttr
```

### enterkeyhint

```saga
fun enterkeyhint : String -> HtmlAttr
```

### headingoffset

```saga
fun headingoffset : Int -> HtmlAttr
```

### inputmode

```saga
fun inputmode : String -> HtmlAttr
```

### is

```saga
fun is : String -> HtmlAttr
```

### itemid

```saga
fun itemid : String -> HtmlAttr
```

### itemprop

```saga
fun itemprop : String -> HtmlAttr
```

### itemref

```saga
fun itemref : String -> HtmlAttr
```

### itemtype

```saga
fun itemtype : String -> HtmlAttr
```

### lang

```saga
fun lang : String -> HtmlAttr
```

### nonce

```saga
fun nonce : String -> HtmlAttr
```

### part

```saga
fun part : String -> HtmlAttr
```

### popover

```saga
fun popover : String -> HtmlAttr
```

### slot

```saga
fun slot : String -> HtmlAttr
```

### spellcheck

```saga
fun spellcheck : Bool -> HtmlAttr
```

### tabindex

```saga
fun tabindex : Int -> HtmlAttr
```

### translate

```saga
fun translate : String -> HtmlAttr
```

### xml_lang

```saga
fun xml_lang : String -> HtmlAttr
```

### on

```saga
fun on : String -> String -> HtmlAttr
```

### href

```saga
fun href : String -> HtmlAttr
```

### hreflang

```saga
fun hreflang : String -> HtmlAttr
```

### src

```saga
fun src : String -> HtmlAttr
```

### srcset

```saga
fun srcset : String -> HtmlAttr
```

### sizes

```saga
fun sizes : String -> HtmlAttr
```

### imagesrcset

```saga
fun imagesrcset : String -> HtmlAttr
```

### imagesizes

```saga
fun imagesizes : String -> HtmlAttr
```

### alt

```saga
fun alt : String -> HtmlAttr
```

### coords

```saga
fun coords : String -> HtmlAttr
```

### shape

```saga
fun shape : String -> HtmlAttr
```

### title

```saga
fun title : String -> HtmlAttr
```

### rel

```saga
fun rel : String -> HtmlAttr
```

### media

```saga
fun media : String -> HtmlAttr
```

### ping

```saga
fun ping : String -> HtmlAttr
```

### referrerpolicy

```saga
fun referrerpolicy : String -> HtmlAttr
```

### name

```saga
fun name : String -> HtmlAttr
```

### value

```saga
fun value : String -> HtmlAttr
```

### accept

```saga
fun accept : String -> HtmlAttr
```

### accept_charset

```saga
fun accept_charset : String -> HtmlAttr
```

### alpha

```saga
fun alpha : String -> HtmlAttr
```

### autocomplete

```saga
fun autocomplete : String -> HtmlAttr
```

### capture

```saga
fun capture : String -> HtmlAttr
```

### colorspace

```saga
fun colorspace : String -> HtmlAttr
```

### dirname

```saga
fun dirname : String -> HtmlAttr
```

### form_id

```saga
fun form_id : String -> HtmlAttr
```

### formaction

```saga
fun formaction : String -> HtmlAttr
```

### formenctype

```saga
fun formenctype : String -> HtmlAttr
```

### formmethod

```saga
fun formmethod : String -> HtmlAttr
```

### formtarget

```saga
fun formtarget : String -> HtmlAttr
```

### command

```saga
fun command : String -> HtmlAttr
```

### commandfor

```saga
fun commandfor : String -> HtmlAttr
```

### list_id

```saga
fun list_id : String -> HtmlAttr
```

### popovertarget

```saga
fun popovertarget : String -> HtmlAttr
```

### popovertargetaction

```saga
fun popovertargetaction : String -> HtmlAttr
```

### max

```saga
fun max : String -> HtmlAttr
```

### maxlength

```saga
fun maxlength : Int -> HtmlAttr
```

### min

```saga
fun min : String -> HtmlAttr
```

### minlength

```saga
fun minlength : Int -> HtmlAttr
```

### low

```saga
fun low : String -> HtmlAttr
```

### high

```saga
fun high : String -> HtmlAttr
```

### optimum

```saga
fun optimum : String -> HtmlAttr
```

### pattern

```saga
fun pattern : String -> HtmlAttr
```

### placeholder

```saga
fun placeholder : String -> HtmlAttr
```

### size

```saga
fun size : Int -> HtmlAttr
```

### step

```saga
fun step : String -> HtmlAttr
```

### type_

```saga
fun type_ : String -> HtmlAttr
```

### for_

```saga
fun for_ : String -> HtmlAttr
```

### label_attr

```saga
fun label_attr : String -> HtmlAttr
```

### role

```saga
fun role : String -> HtmlAttr
```

### aria

```saga
fun aria : String -> String -> HtmlAttr
```

### data_

```saga
fun data_ : String -> String -> HtmlAttr
```

Creates a data-* attribute.

### data_attr

```saga
fun data_attr : String -> HtmlAttr
```

### style

```saga
fun style : String -> HtmlAttr
```

### method

```saga
fun method : String -> HtmlAttr
```

### action

```saga
fun action : String -> HtmlAttr
```

### enctype

```saga
fun enctype : String -> HtmlAttr
```

### target

```saga
fun target : String -> HtmlAttr
```

### charset

```saga
fun charset : String -> HtmlAttr
```

### content

```saga
fun content : String -> HtmlAttr
```

### http_equiv

```saga
fun http_equiv : String -> HtmlAttr
```

### property

```saga
fun property : String -> HtmlAttr
```

### cite

```saga
fun cite : String -> HtmlAttr
```

### datetime

```saga
fun datetime : String -> HtmlAttr
```

### cols

```saga
fun cols : Int -> HtmlAttr
```

### rows

```saga
fun rows : Int -> HtmlAttr
```

### wrap

```saga
fun wrap : String -> HtmlAttr
```

### colspan

```saga
fun colspan : Int -> HtmlAttr
```

### rowspan

```saga
fun rowspan : Int -> HtmlAttr
```

### headers

```saga
fun headers : String -> HtmlAttr
```

### scope

```saga
fun scope : String -> HtmlAttr
```

### abbr

```saga
fun abbr : String -> HtmlAttr
```

### height

```saga
fun height : Int -> HtmlAttr
```

### width

```saga
fun width : Int -> HtmlAttr
```

### loading

```saga
fun loading : String -> HtmlAttr
```

### decoding

```saga
fun decoding : String -> HtmlAttr
```

### crossorigin

```saga
fun crossorigin : String -> HtmlAttr
```

### integrity

```saga
fun integrity : String -> HtmlAttr
```

### as_

```saga
fun as_ : String -> HtmlAttr
```

### defer

```saga
fun defer : HtmlAttr
```

### async_

```saga
fun async_ : HtmlAttr
```

### nomodule

```saga
fun nomodule : HtmlAttr
```

### poster

```saga
fun poster : String -> HtmlAttr
```

### preload

```saga
fun preload : String -> HtmlAttr
```

### controlslist

```saga
fun controlslist : String -> HtmlAttr
```

### kind

```saga
fun kind : String -> HtmlAttr
```

### srclang

```saga
fun srclang : String -> HtmlAttr
```

### sandbox

```saga
fun sandbox : String -> HtmlAttr
```

### allow

```saga
fun allow : String -> HtmlAttr
```

### blocking

```saga
fun blocking : String -> HtmlAttr
```

### color

```saga
fun color : String -> HtmlAttr
```

### fetchpriority

```saga
fun fetchpriority : String -> HtmlAttr
```

### srcdoc

```saga
fun srcdoc : String -> HtmlAttr
```

### usemap

```saga
fun usemap : String -> HtmlAttr
```

### start

```saga
fun start : Int -> HtmlAttr
```

### span_attr

```saga
fun span_attr : Int -> HtmlAttr
```

### shadowrootmode

```saga
fun shadowrootmode : String -> HtmlAttr
```

### shadowrootslotassignment

```saga
fun shadowrootslotassignment : String -> HtmlAttr
```

### allowfullscreen

```saga
fun allowfullscreen : HtmlAttr
```

### download

```saga
fun download : HtmlAttr
```

### download_as

```saga
fun download_as : String -> HtmlAttr
```

### disabled

```saga
fun disabled : HtmlAttr
```

### checked

```saga
fun checked : HtmlAttr
```

### selected

```saga
fun selected : HtmlAttr
```

### readonly

```saga
fun readonly : HtmlAttr
```

### required

```saga
fun required : HtmlAttr
```

### autofocus

```saga
fun autofocus : HtmlAttr
```

### hidden

```saga
fun hidden : HtmlAttr
```

### headingreset

```saga
fun headingreset : HtmlAttr
```

### inert

```saga
fun inert : HtmlAttr
```

### itemscope

```saga
fun itemscope : HtmlAttr
```

### multiple

```saga
fun multiple : HtmlAttr
```

### formnovalidate

```saga
fun formnovalidate : HtmlAttr
```

### novalidate

```saga
fun novalidate : HtmlAttr
```

### open_

```saga
fun open_ : HtmlAttr
```

### controls

```saga
fun controls : HtmlAttr
```

### autoplay

```saga
fun autoplay : HtmlAttr
```

### loop

```saga
fun loop : HtmlAttr
```

### muted

```saga
fun muted : HtmlAttr
```

### playsinline

```saga
fun playsinline : HtmlAttr
```

### default_

```saga
fun default_ : HtmlAttr
```

### reversed

```saga
fun reversed : HtmlAttr
```

### ismap

```saga
fun ismap : HtmlAttr
```

### shadowrootdelegatesfocus

```saga
fun shadowrootdelegatesfocus : HtmlAttr
```

### shadowrootclonable

```saga
fun shadowrootclonable : HtmlAttr
```

### shadowrootserializable

```saga
fun shadowrootserializable : HtmlAttr
```

### shadowrootcustomelementregistry

```saga
fun shadowrootcustomelementregistry : HtmlAttr
```

### html

```saga
fun html : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### head_

```saga
fun head_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### body

```saga
fun body : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### title_

```saga
fun title_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### style_

```saga
fun style_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### script

```saga
fun script : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### noscript

```saga
fun noscript : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### div

```saga
fun div : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### span

```saga
fun span : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### p

```saga
fun p : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### a

```saga
fun a : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### abbr_el

```saga
fun abbr_el : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### address

```saga
fun address : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h1

```saga
fun h1 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h2

```saga
fun h2 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h3

```saga
fun h3 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h4

```saga
fun h4 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h5

```saga
fun h5 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### h6

```saga
fun h6 : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### hgroup

```saga
fun hgroup : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### b

```saga
fun b : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### bdi

```saga
fun bdi : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### bdo

```saga
fun bdo : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### blockquote

```saga
fun blockquote : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### cite_el

```saga
fun cite_el : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### code

```saga
fun code : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### data_el

```saga
fun data_el : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### del

```saga
fun del : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### dfn

```saga
fun dfn : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### em

```saga
fun em : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### i

```saga
fun i : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### ins

```saga
fun ins : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### kbd

```saga
fun kbd : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### mark

```saga
fun mark : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### pre

```saga
fun pre : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### q

```saga
fun q : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### rp

```saga
fun rp : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### rt

```saga
fun rt : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### ruby

```saga
fun ruby : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### s

```saga
fun s : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### samp

```saga
fun samp : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### small

```saga
fun small : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### strong

```saga
fun strong : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### sub

```saga
fun sub : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### sup

```saga
fun sup : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### time

```saga
fun time : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### u_

```saga
fun u_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### var_

```saga
fun var_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### ul

```saga
fun ul : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### ol

```saga
fun ol : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### li

```saga
fun li : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### menu

```saga
fun menu : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### dl

```saga
fun dl : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### dt

```saga
fun dt : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### dd

```saga
fun dd : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### nav

```saga
fun nav : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### main_

```saga
fun main_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### search

```saga
fun search : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### section

```saga
fun section : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### article

```saga
fun article : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### header

```saga
fun header : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### footer

```saga
fun footer : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### aside

```saga
fun aside : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### figure

```saga
fun figure : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### figcaption

```saga
fun figcaption : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### details

```saga
fun details : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### summary

```saga
fun summary : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### dialog

```saga
fun dialog : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### button

```saga
fun button : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### form

```saga
fun form : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### fieldset

```saga
fun fieldset : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### legend

```saga
fun legend : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### label

```saga
fun label : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### textarea

```saga
fun textarea : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### select

```saga
fun select : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### datalist

```saga
fun datalist : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### optgroup

```saga
fun optgroup : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### option

```saga
fun option : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### output

```saga
fun output : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### progress

```saga
fun progress : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### meter

```saga
fun meter : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### table

```saga
fun table : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### caption

```saga
fun caption : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### colgroup

```saga
fun colgroup : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### thead

```saga
fun thead : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### tbody

```saga
fun tbody : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### tfoot

```saga
fun tfoot : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### tr

```saga
fun tr : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### th

```saga
fun th : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### td

```saga
fun td : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### canvas

```saga
fun canvas : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### audio

```saga
fun audio : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### video

```saga
fun video : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### picture

```saga
fun picture : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### map_

```saga
fun map_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### object_

```saga
fun object_ : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### iframe

```saga
fun iframe : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### slot_el

```saga
fun slot_el : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### template

```saga
fun template : List HtmlAttr -> List HtmlNode -> HtmlNode
```

### selectedcontent

```saga
fun selectedcontent : List HtmlAttr -> HtmlNode
```

### meta

```saga
fun meta : List HtmlAttr -> HtmlNode
```

### base

```saga
fun base : List HtmlAttr -> HtmlNode
```

### link

```saga
fun link : List HtmlAttr -> HtmlNode
```

### area

```saga
fun area : List HtmlAttr -> HtmlNode
```

### img

```saga
fun img : List HtmlAttr -> HtmlNode
```

### input

```saga
fun input : List HtmlAttr -> HtmlNode
```

### br

```saga
fun br : List HtmlAttr -> HtmlNode
```

### hr

```saga
fun hr : List HtmlAttr -> HtmlNode
```

### col

```saga
fun col : List HtmlAttr -> HtmlNode
```

### embed

```saga
fun embed : List HtmlAttr -> HtmlNode
```

### source

```saga
fun source : List HtmlAttr -> HtmlNode
```

### track

```saga
fun track : List HtmlAttr -> HtmlNode
```

### wbr

```saga
fun wbr : List HtmlAttr -> HtmlNode
```

