# Coastal-Zeta
This repository contains R code that generated the boxplots in Figures 1a and the scatterplots and line fits in Figure 1b in the paper titled "Bioturbation enhances bacterial iron oxidation in coastal marine sediments".

Figure 1a
boxplot(zeta$worm.burrow, zeta$sediment, names=c("Worm burrow", "Sediment"), col=c("orange", "grey"), ylab="Zetaproteobacteria Relative Abundance (%)", notch=TRUE)
stripchart(zeta$worm.burrow, method='jitter', vertical=TRUE, add=TRUE, at=1:1, pch=16, cex=1.5, col=c("blue")
stripchart(zeta$sediment, method='jitter', vertical=TRUE, add=TRUE, at=2:2, pch=16, cex=1.5, col=c("black")

Figure 1b
ggplot(data=ZetaFe) + geom_jitter(aes(Fe,worm.burrow), colour="blue") + geom_point(aes(Fe,worm.burrow), size=3, colour="blue") + geom_jitter(aes(Fe,sediment), colour="black") + geom_point(aes(Fe,sediment), size=3 colour="black") + geom_smooth(method="loess", span=10, colour="black", fill="grey", aes(Fe,sediment)) + ylab("Zetaproteobacteria relative abundance (%)") + xlab("Fe (umol L-1)") + theme_bw() + geom_smooth(method="glm" method.args=list(family=gaussian(link="log")), fill="orange", aes(Fe,worm.burrow))
