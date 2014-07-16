# Velocity Print SVG Macro

This macro is used to fetch a SVG file, optionally change the <svg> tag's attributes and render it's html

## USE:

You will fist need to include the print-svg.vtl file like so:

 	#dotParse( '/pathToFile/print-svg.vtl'  )##

Then you can just call the SVG in your template where ever you want it to show up:

	#printSVG( $path $attributesObject )##

The macro accepts two arguments. The first "$path" can be either an established common name reference for a SVG that you have added to the $knownSvgList in the core code. This is just a short cut for ease of use within your team. You can alternatively pass a string that is the root relative path to your svg. 

	## COMMON NAME
	#printSVG( 'svgCommonName' )## this will check the list of commonly used SVGs for an available src
	## ROOT RELATIVE PATH
	#printSVG( '/common/svg/icon.svg' )## you can also enter a relative path the the desired SVG

The second argument you can pass to the macro is an object of html svg attribute value pairs, like so:

	#printSVG( $path {'height':'200px', 'width':'100%', 'viewBox':''} )

Note that for `viewBox` the empty value will tell the macro to delete that attribute. In contrast the `height` and `width` properties will just be updated to the defined values. 

And that is all there is to it :-)
