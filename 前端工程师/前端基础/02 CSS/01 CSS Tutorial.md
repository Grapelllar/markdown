# CSS Tutorial

## CSS Introduction

* CSS stands for Cascading Style Sheets,it describes how HTML elements are to be displayed on website.

## CSS Syntax

* 

![cssSyntax](D:\NEW\Study\markdown\pic\css\cssSyntax.png)

## CSS Selectors

* CSS Selectors divide into five categories：

  * Simple selectors（element、class、id、*（universal））
  * Combinator selectors（space、>、+、~，based on relationship）
  * Pseudo-class selectors（':'，based on a certain state，like visit、visited）
  * Pseudo-element selectors（'::'，style a part of an element）
  * Attribute selectors（'a[target]'，select an attribute or attribute value for an element）

* Simple Selectors：

  * CSS element Selector，it just write element name on the beginning of one line

  * CSS id Selector，write a hash(#)

  * CSS class Selector，write a period(.)
  * CSS Universal Selector，write a *

* CSS Selector also can be grouping like this: h1,h2,p, they will have same style.

## How to Add CSS

* There are three ways to inserting a style sheet：
  * External CSS，it saves on external directory.
  * Internal CSS，it contains on head tag.
  * Inline CSS，it writes on element tag , using style attribute.
* If some properties have been defined for the same selector in different style sheets , the value from the last read style sheet will be used. And inline style has the highest priority when override.

## CSS Comments

* A CSS comment starts with /* and end with */
* It is different from HTML , A HTML comment using <!--...--> syntax.

## CSS Colors

* Colors are specified using predefined color names , or RGB , HEX , HSL , RGBA , HSLA valus.
* RGB、HEX、HSL
  * RGB color value represents RED\GREEN\BLUE light sources.
  * RGBA has another attribute opacity , the A meas alpha.

