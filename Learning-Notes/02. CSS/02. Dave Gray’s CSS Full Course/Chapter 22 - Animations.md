---
tags:
  - WebDev
---
Going to be learning about animations, transforms, and transitions.

*Goes over all the HTML (3) and CSS (2) files and what they contain*

[Transform Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* This property lets you rotate, scale, skew, or translate an element. It modifies the coordinate space of the CSS visual formatting model.
	* Example: `transform: rotate(1.2);`

[TranslateX Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateX)
* This function repositions an element horizontally on the 2D plane. Its result is a `<transform-function>` data type.
	* Example: `transform: translateX(12px);`

[TranslateY Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateY)
* This function repositions an element vertically on the 2D plane. Its result is a `<transform-function>` data type.
	* Example: `transform: translateY(12px);`

[Translate Shorthand Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate)
* This shorthand function repositions an element in the horizontal (X) and/or vertical directions (Y). Its result is a `<transform-function>` data type.
	* Example: `transform: translate(12px, 15px);`

[Rotate Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate)
* This function defines a transformation that rotates an element around a fixed point on the 2D plane, without deforming it. Its result is a `<transform-function>` data type.
	* Example: `transform: rotate(90deg);`

[RotateX Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateX)
* This function defines a transformation that rotates an element around the x-axis (horizontal) without deforming it. Its result is a `<transform-function>` data type.
	* Example: `transform: rotateX(180deg);`

[RotateY Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateY)
* This function defines a transformation that rotates an element around the y-axis (vertical) without deforming it. Its result is a `<transform-function>` data type.
	* Example: `transform: rotateY(45deg);`

[RotateZ Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateZ)
* This function defines a transformation that rotates an element around the z-axis without deforming it. Its result is a `<transform-function>` data type.
	* Example: `transform: rotateZ(0);`

[Rotate Shorthand Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/rotate)
* This property allows you to specify rotation transforms individually and independently of the `transform` property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` property.
	* Example: `rotate: 3 .5 2 45deg;`

[ScaleX Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleX)
* This function defines a transformation that resizes an element along the x-axis (horizontally). Its result is a `<transform-function>` data type.
	* Example: `transform: scaleX(1.2);`

[ScaleY Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleY)
* This function defines a transformation that resizes an element along the y-axis (vertically). Its result is a `<transform-function>` data type.
	* Example: `transform: scaleY(1);`

[ScaleZ Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleZ)
* This function defines a transformation that resizes an element along the z-axis. Its result is a `<transform-function>` data type.
	* Example: `transform: scaleZ(1);`

[Scale Shorthand Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/scale)
* property allows you to specify scale transforms individually and independently of the `transform` property. This maps better to typical user interface usage, and saves having to remember the exact order of transform functions to specify in the `transform` value.
	* Example: `scale: 1.2 1.2 2;`

[SkewX Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewX)
* This function defines a transformation that skews an element in the horizontal direction on the 2D plane. Its result is a `<transform-function>` data type.
	* Example: `transform: skewX(0);`

[SkewY Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewY)
* This function defines a transformation that skews an element in the vertical direction on the 2D plane. Its result is a `<transform-function>` data type.
	* Example: `transform: skewY(35deg);`

[Skew Shorthand Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew)
* This function defines a transformation that skews an element on the 2D plane. Its result is a `<transform-function>` data type.
	* Example: `transform: skew(15deg, 15deg);`

[Transition Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* This property is a shorthand property for `transition-property`, `transition-duration`, `transition-timing-function`, `transition-delay`, and `transition-behavior`.
	* Example: `transition: margin-right 2s ease-in-out .5s;`

[Transition-Duration Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration)
* This property sets the length of time a transition animation should take to complete. By default, the value is `0s`, meaning that no animation will occur.
	* Example: `transition-duration: 500ms;`

[Transition-Delay Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay)
* This property specifies the duration to wait before starting a property's transition effect when its value changes.
	* Example: `transition-delay: 1s;`

[Animation Shorthand Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* This shorthand CSS property applies an animation between styles. It is a shorthand for `animation-name`, `animation-duration`, `animation-timing-function`, `animation-delay`, `animation-iteration-count`, `animation-direction`, `animation-fill-mode`, `animation-play-state`, and `animation-timeline`.
	* Example: `animation: 3s ease-in 1s infinite reverse both running slidein;`

[@Keyframes Property - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
* This at-rule controls the intermediate steps in a CSS animation sequence by defining styles for keyframes (or waypoints) along the animation sequence. This gives more control over the intermediate steps of the animation sequence than transitions.
	* Refer to example in the link provided