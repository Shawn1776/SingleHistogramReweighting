# SingleHistogramReweighting
single histogram reweighing

1) construct the simulating system (L, N, E, M , Temperature) and let it rearch equilibrium 
2) run MC run, and construct your histogram (statics or dynamics??), H_t1 (minE, maxE, bucketNum, bucketSize, Eavg for each bucket etc.)
3) after you have the histogram of centain temperature, you can use it to the E distribution of desired P_temperature2. (P_t2)

P_t2 = Pt2_nominator / Pt2_denominator

Pt2_nominator = [ H_t1(i) / Sum(H_t1(i)) ] * Exp(Ei(1.0/T1-1.0/T2)) // normalized H_t(i) * Boltzmann factor  

Where i is the index of the bucket of the histogram

Pt2_denominator= Sum of Pt2_nominator

4) then, E_avg= Pt2(i)*Eb_avg(i), E*E_avg = Pt2(i)*Eb_avg(i)*Eb_avg(i) // i again is the bucket and Eb_avg(i) is the avg of the i th bucket of Pt2

5) Cv_t2= (E*E_avg - E_avg*E_avg) / (t2*t2*N)

