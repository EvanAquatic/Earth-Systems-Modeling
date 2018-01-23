# Earth-Systems-Modeling
R

#https://rdrr.io/cran/seacarb/man/bjerrum.html

library(seacarb)

## Plot the bjerrum plot for the carbonate system using the default values
bjerrum(K1(6.35),K2(10.33),,conc=2.65, main="Polyprotic Acid H2CO3 Speciation",lwd=2) 
abline(v=-log10(K1(6.35)),col="grey")
mtext(side=3,at=-log10(K1(6.35)),"pK1")
abline(v=-log10(K2(10.33)),col="grey")
mtext(side=3,at=-log10(K2(10.33)),"pK2")
legend("left",lty=1:3,lwd=2,legend=c(expression(CO[2]),expression(HCO[3]^"-"),expression(CO[3]^"2-")))
