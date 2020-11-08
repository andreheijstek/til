# Migration problems 

Soms lukt het niet om een migration te draaien. Foutmelding: tabel bestaat al.
Vermoedelijk ontstaat dit als je in een branch een migration gemaakt hebt en dan weer mergt naar main (hoewel ik dit niet zeker weet).
Iig is de oplossing om de database weer opnieuw op te bouwen:
    rake db:drop
    rake db:create
    rake db:migrate
    rake db:seed
