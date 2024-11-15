## React Events

React events are the actions due to user interaction or system events.
React allows developers to handle these events using a declarative approach, making it easier to create interactive and dynamic user interfaces.

React events syntax is in camelCase, not lowercase. If we need to set events in our code, we have to pass them, just like props or attributes, to JSX or HTML.

passing object - ``onSubmit={function}`` 

event object - ``onSubmit={()=>{function(argument)}}``

**Example:**

**1. Clipboard Events**
``onCopy``
``onCut``
``onPaste``

**2. Composition Events**
``onCompositionEnd``
``onCompositionStart``
``onCompositionUpdate``

**3. Focus Events**
``onFocus``
``onBlur``

**4. Form Events**
``onChange``
``onInput``
``onInvalid``
``onReset``
``onSubmit``

**5. Keyboard Events**
``onKeyDown``
``onKeyPress`` (Deprecated; use onKeyDown or onKeyUp)
``onKeyUp``

**6. Mouse Events**
``onClick``
``onContextMenu``
``onDoubleClick``
``onDrag``
``onDragEnd``
``onDragEnter``
``onDragExit``
``onDragLeave``
``onDragOver``
``onDragStart``
``onDrop``
``onMouseDown``
``onMouseEnter``
``onMouseLeave``
``onMouseMove``
``onMouseOut``
``onMouseOver``
``onMouseUp``

**7. Pointer Events**
``onPointerDown``
``onPointerMove``
``onPointerUp``
``onPointerCancel``
``onPointerEnter``
``onPointerLeave``
``onPointerOver``
``onPointerOut``

**8. Selection Events**
``onSelect``

**9. Touch Events**
``onTouchCancel``
``onTouchEnd``
``onTouchMove``
``onTouchStart``

**10. UI Events**
``onScroll``

**11. Wheel Events**
``onWheel``

**12. Media Events**
``onAbort``
``onCanPlay``
``onCanPlayThrough``
``onDurationChange``
``onEmptied``
``onEncrypted``
``onEnded``
``onLoadedData``
``onLoadedMetadata``
``onLoadStart``
``onPause``
``onPlay``
``onPlaying``
``onProgress``
``onRateChange``
``onSeeked``
``onSeeking``
``onStalled``
``onSuspend``
``onTimeUpdate``
``onVolumeChange``
``onWaiting``

**13. Image Events**
``onLoad``
``onError``

**14. Animation Events**
``onAnimationStart``
``onAnimationEnd``
``onAnimationIteration``

**15. Transition Events**
``onTransitionEnd``











