# VDP

http://andreavogrig.com/vdp/

Javascript implementation of a driven coupled Van Der Pol oscillator using Web Audio API.

In dynamics, the Van Der Pol oscillator is a non-conservative oscillator with non-linear damping. It evolves in time according to the following second-order differential equations:
		
    y''(t) + u(1-y(t)*y(t))* y'(t) + y(t) = 0

    t = time
    u = mu (scaling factor)
    y   = displacement
    y'  = velocity     // first derivate
    y'' = acceleration // second derivate

The forced, or driven, Van Der Pol oscillator takes the original function and adds a driving function Asin(wt):

    y'' - u(1-y*y) * y'+ y = a cos(wt)

Driven Van der Pol equations:

    y1'' - u(1-y1*y1) * y1'+ y1 = a cos(wt)
    y2'' - u(1-y2*y2) * y2'+ y2  = a cos(wt)

for undriven oscillator, set a = 0

coupling:

	k = (0.1-1.0) scaling factor to limit coupling

    y1 = y1 - y2 * k
    y1' = y1' + y2' * k
    y1'' = y1'' + y2' * k
    y2 = y1 - y1 * k
    y2' = y2' + y1' * k
    y2'' = y2'' + y1' * k

The phase plane plotting is achieved using “stereo-analyser-node.min.js” an audio node capable of analyzing stereo audio signals.
The graphical user interface (GUI) is made using dat.GUI: A lightweight graphical user interface for changing variables in JavaScript.

# References:
 - VanDerPol (https://en.wikipedia.org/wiki/Van_der_Pol_oscillator)
 - Fortran Implementation (http://www.phy.mtu.edu/~suits/PH3110/vderpol.pdf)
 - odex (http://blog.littleredcomputer.net/math/odex/js/2016/04/20/van-der-pol.html)
 - Web audio API (https://www.w3.org/TR/webaudio/)
 - Stereo analyzer (https://www.npmjs.com/package/stereo-analyser-node)
 - dat.GUI (https://github.com/dataarts/dat.gui)

# Credits:
  M▨DD
