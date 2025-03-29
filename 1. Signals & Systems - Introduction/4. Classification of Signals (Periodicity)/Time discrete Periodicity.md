# Time discrete Periodicity

## Remember

$t = nT_s$ , n $\varepsilon$ $\mathbb{Z}^{+}$

Thus

$\cos[\omega nT_s] = \cos[\frac{2\pi}{T} nT_s]$

$\cos[\omega nT_s] = \cos[2\pi F \frac{n}{F_s}]$

$\cos[\omega nT_s] = \cos[2\pi \frac{F}{F_s} n]$

Thus, the frequency in discrete time is $\frac{\frac{1}{s}}{\frac{1}{s}} = \frac{1 cycle}{1 sampling} = [\frac{cycles}{samplings}]$

In words, how many samplings represent one cycle 

So $2\pi fn = \theta [n]$ , the angle is in function of samplings

## angular frequency in discrete time

$\cos [\Omega n]$ ; $\Omega = 2\pi f [\frac{rad*cycles}{samplings}]$

# Periodic signal in discrete time

It must be $\cos[\Omega n]$ = $\cos[\Omega [n \pm N]]$

## Period in discrete time

$N$ 

So, $f = \frac{F}{F_s} = \frac{1}{N}$

## Exercise

Prove that $\cos[\Omega n]$ is periodic

**Solution**

$\cos[\Omega n] = \cos[\Omega[n \pm N]]$

$\cos[\Omega n] = \cos[2\pi f[n \pm N]]$

$\cos[\Omega n] = \cos[2\pi fn \pm 2\pi fN]]$

where $\alpha = 2\pi fn$ and $\beta = 2\pi fN$

So, aplying the trigonometry identity

$\cos(\alpha \pm \beta) = \cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta)$ 

Thus

$\cos(2\pi fn \pm 2\pi fN ) = \cos(2\pi fn)\cos(2\pi fN) \mp \sin(2\pi fn)\sin(2\pi fN)$ 

where $\cos(2\pi fN) = 1$ and $\sin(2\pi fN) = 0$

Thus

$\cos(2\pi fn \pm 2\pi fN ) = \cos(2\pi fn) 

$\cos[\Omega[n \pm N]] = \cos[\Omega n]$; if  $\Omega =2\pi f$ and $N = \frac{1}{f}$, sames f
