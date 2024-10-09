#GeneralProgramming 

---
Euclid's life was not very well documented, we now he probably studied in Plato's *Academy* in Athens sometime after his death and that he took geometry very seriously. He brought his knowledge to Alexandria, where he wrote *Elements*, one of the most influential mathematical books of the time. 

##### *Euclid's Greatest Common Measure*
Book *X* of Euclid's *Elements* contained a concise treatment of incommensurable quantities:

> **Proposition 2.** If, when the less of two unequal magnitudes is continually subtracted in turn from the greater, that which is left never measures the one before it, then the two magnitudes are incommensurable.

Basically saying that if our procedure of finding the greatest common measure never ends, then there is no common measure. Then Euclid goes on to describe the algorithm that computes the GCM. The first algorithm termination proof in history goes as follows, translated by Sir Thomas Heath's:

> **Proposition 3.** Given two commensurable magnitudes, to find their greatest common measure.
> *Proof.*
> Let the two given commensurable magnitudes be AB, CD of which AB is the less; thus it is required to find the greatest common measure of AB, CD.

[[Euclid's GCM Diagram]]
![[Pasted image 20241009102315.png]]
> Now the magnitude AB either measures CD or not.
> If then it measures it - and it measures itself also - AB is a common measure of AB, CD.
> And it is manifest that it is also the greatest; For a greater magnitude than the magnitude AB will not measure AB.
> 