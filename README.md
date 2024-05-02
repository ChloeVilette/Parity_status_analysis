# Parity_status_analysis
You will find the r code, as well as the data files that were used to conduct this analysis. 



### MODEL STRUCTURE ###

These are the following model structures used to answer our five questions. 

    QUESTION 1: Grooming network structure comparisons between juvenile and adult females

        With the juvenile grooming data

    response_variable ~ s(age, m=2) + s(age, ID, bs="fs", m=1)+ s(cohortID, bs="re",k=3) + s(troopID, bs="re", k=3)+ s(age, mumID, bs="fs", m=1) + s(scan.nb, bs="tp")+ s(ndvi, bs="tp") +s(troop.nb, bs="tp")+s(rank, bs="tp")
    

        With the adult grooming data

    response_variable ~ (day.nb, m=2) +  s(day.nb, ID, bs="fs", m=1)+ s(troopID, bs="re", k=3)+ s(yday, bs="cc") + s(scan.nb, bs="tp") + s(ndvi, bs="tp") +s(troop.nb, bs="tp") + s(rank, bs="tp")



    QUESTION 2: Grooming network structure comparisons between primiparous and multiparous females around birth event

    response_variable ~ s(time, bs="tp") + s(time, by = primiparous, m=1, bs="tp")+ s(primiparous, bs="re", k=2) +s(ID, bs="re")+ s(troopID,bs="re",k=3) + s(scan.nb,bs="tp", k=3) + s(troop.nb, bs="tp") + s(ndvi, bs="tp") + s(rank, bs="tp") + s(year, bs="re",k=6)

    

    QUESTION 3: Females' social integration around birth event

    response_variable ~ s(time, bs="tp") + s(time, by = primiparous, m=1, bs="tp")+ s(primiparous, bs="re", k=2) +s(ID, bs="re")+ s(troopID,bs="re",k=3) + s(scan.nb,bs="tp", k=3) + s(troop.nb, bs="tp") + s(ndvi, bs="tp") + s(rank, bs="tp") + s(year, bs="re",k=6)

    

    QUESTION 4: Grooming bubble (strong ties) and weak ties structures

    response_variable ~ s(time, bs="tp") + s(time, by = primiparous, m=1, bs="tp")+ s(primiparous, bs="re", k=2) +s(ID, bs="re")+ s(troopID,bs="re",k=3) + s(scan.nb,bs="tp", k=3) + s(troop.nb, bs="tp") + s(ndvi, bs="tp") + s(rank, bs="tp") + s(year, bs="re",k=6)

    

    QUESTION 5: Knockout analysis

    response_variable ~ variable*primiparous+ (1|troop) +(1|ID) +scan.nb + troop.nb + (1|year) + ndvi +rank + start.eigen

    
