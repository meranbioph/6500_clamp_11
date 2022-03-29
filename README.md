CLAMP_11: Respiration and Convection only

Mesh: super coarse mesh (2688 cells)
OpenFOAM version: 9
Solver: clampPimpleFoam

Case clamp_11 was developed following the issues noted at from the testing of the coarse meshes in cases clamp_09 and clamp_10. Peer review/ revisit parameters also resulted in some minor updates.

Updates:
Noteworthy
- Qr functional form update from exponential to logistic.
- The heat transfer between phases updated in solver clampPimpleFoam v3 to include the porosity. A new fixed scalar, invPor was added to the system (owing to a lack of programming smarts - using 1-por in Ts would give a div-by-0 siutation, this avoids that). This change has also been added to v2 of the solver and invPor added to cases back to clamp_06.
- the number of non-orthogonal correctors increased in fvSolution from 0 to 1. The number of nCorrectors was also increased from 2 to 3.

Minor
- initial velocity and temperature (Tf) reflect the constant inlet conditions - implemented retrosectively to clamp_05.
- update of Ks from 0.53 to 0.554 - implemented retrosectively to clamp_05.
- update of Deq to 0.13786 from 0.06399 - implemented retrosectively to clamp_08.
