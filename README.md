# Final Project Assignment 2: Exploration (FP2)
DUE Wednesday, March 23, 2016

## My Library: plot: graph plotting
My name: Samir Khoulani

The next topic I was interested in was the plot libary, as I remain interested in calculus in general. To begin, I experimented with 2D graphing. I played around with a sinusoidal function, and its bounds, and came up with something simple as shown in <b>Fig. 1</b>. The code for this first exercise:
```racket
(plot (function cos (- (/ pi 2)) (/ pi 2) #:label "y = cos(x)"))
```
The next thing I moved to was plotting in 3D. I attempted to plot more than one sphere in the same graph, but was unable to because of the incorrect syntax I was using to list them. This was in part due to the incorrect placement of the x,y, and z minima and maxima definititions.

```racket
;First failed attempt at plotting multiple 3-D graphs. Plotted three
(plot3d (list
         (axes)
         ((polar3d (λ (θ ρ) 1) #:color 2 #:line-style 'transparent)
          #:x-min -0.3 #:x-max 0.8
          #:y-min -0.3 #:y-max 0.8
          #:z-min -0.3 #:z-max 0.8
          #:altitude 25)
        ((polar3d (λ (θ ρ) 1) #:color 1 #:line-style 'transparent)
          #:x-min -0.2 #:x-max 0.5
         #:y-min -0.2 #:y-max 0.5
          #:z-min -0.2 #:z-max 0.5
          #:altitude 25)
        ((polar3d (λ (θ ρ) 1) #:color 3 #:line-style 'transparent
          #:x-min -0.7 #:x-max 0.8
          #:y-min -0.7 #:y-max 0.8
          #:z-min -0.7 #:z-max 0.8
          #:altitude 25))))
```


Moving further through the library brought me to the correct method of plotting 3D graphs in the same window. 

This first was done by calculating the distance formula: 
```racket
(define ((dist cx cy cz) x y z)
    (sqrt (+ (sqr (- x cx)) (sqr (- y cy)) (sqr (- z cz)))))
```

After this was done, it was a matter of creating a list of 3D isosurfaces that each held an object. My goal was to make them all intersect in a unique pattern, and the results of different values for the distance formula can be seen in <b>Fig. 2</b> and <b>Fig. 3</b>.

