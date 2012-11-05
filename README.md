WinBUGS Bayesian Estimation using WinBUGS

##BUGScode
##hierarchical linear model
##sample code

##WinBUGS model part
=======

model{
   for(j in 1:10){
   for(i in 1:50){
   y1[i,j]~dnorm(mu1[j],tau1[j])
   }

   sig2[j]<-1/tau1[j]
   mu1[j]~dnorm(M,T)
   tau1[j]~dgamma(.1,.1)
   }
 
   SIG2<-1/T
   M~dnorm(0,.01)
   T~dgamma(.1,.1)
   }