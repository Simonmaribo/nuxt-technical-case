Started using types, but realised the Nuxt Projects wasn't initialized with TypeScript,
so i'm gonna use vanilla for this project.

Cannot use types in the projects, so i compute the values to make sure that they are not null. (and set default values)

Har aldrig rigtigt været helt nede i DOM når det angår sådanne ting her.
så det var lidt spændende hvordan jeg lige skulle løse problemet.

Selve draggable container:
- Første tanke var jeg skulle ind og lave noget avanceret med .getBoundingClientRect() og absolute position, hvilket mislykkedes totalt :D
- Jeg afprøvede så med flexboxes, at få det til at overflow, så der kom en scrollbar, som jeg så kunne imitere.


Case-"svaret" indeholder 3 DraggableContainer-filer, med hver sin fremgangsmåde,
hvor af "first" & "second" blot er skitser for hvordan jeg havde tænkt mig,
at det skulle virke :D