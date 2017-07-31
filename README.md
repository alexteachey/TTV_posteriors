# TTV_posteriors

Collection of transit timing variation (TTV) posteriors for a collection of KOIs analyzed in Teachey, Kipping, and Schmitt 2017 (submitted to AJ July 26, 2017). 

Note that these include more than the 284 planets used in the final Grand Light Curve analysis of that work. A cross-check against false positives is advised if you intend to use these. See https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=koifpp

And of course please cite our paper (https://arxiv.org/abs/1707.08563) if you use these data for your work.


IMPORTANT NOTES:
1) Columns are Rp/Rstar (p), stellar density (rhostar), impact parameter (b), planetary period (Pp, fixed value from NEA), reference epoch (tau_ref, fixed value), two limb darkening coefficients (q1 and q2), and transit times (tau).

2) The fits were performed in segments for planets with > 10 transits. Segments are indicated as seg0, seg1, seg2, etc. Please note that each segment was fit totally independently, so even though transit times for seg0 and seg1 are listed on the same row, they are NOT a single draw from the joint posteriors. One may be a good fit while the other is not, so you should draw from segments independently. Each planet segment contains 10^4 draws from the posteriors. 

3) SegN_tauM is the Mth transit in the Nth segment, and is in the format BJD - 2400000.

4) tau_ref is the reference transit midtime, and is likely the middle epoch (if the planet has 20 transits, tau_ref is probably around epoch 10). To calculate offset from linear ephemeris for seg2_tau3 (for example), we recommend using the median or maximum a posteriori value from seg0_tau3 and calculating

offset_seg2_tau3 = seg2_tau3 - (seg0_tau_ref + N*Pp)

where Pp is the period of the planet and N is an integer that minimizes the value of the offset. Be careful with the sign!
