# open5gs_srsRAN
Simulation d'un réseau 5g/4g: conteneurisation grace à DOCKER de open5gs et srsRAN  et orchestration avec kubernetes
On a conteneurisé la partie acces de notre reseau avec Docker (srsran-docker).
Pour la partie coeur en plus d'être conteneuriser(open5gs-docker), on a essayer de le deployer dans le cloud avec kubernetes
On a utilisé zeroMQ pour remplacer la liaison radio entre l'eNodeB et l'UE.
on a pas pu deployer le montoring avec prometheus par contrainte de temps
