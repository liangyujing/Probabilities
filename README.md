# Show data
HairEyeColor                                               
#Note regarding output: The data, HairEyeColor, are in a 3-dimensional array, with two layers for Male and Female.


# Sum across sex
EyeHairFreq = apply(HairEyeColor, c("Eye", "Hair"), sum)   


# Joint proportions
EyeHairProp = EyeHairFreq / sum(EyeHairFreq)                
show(round(EyeHairProp, 2))

#Note regarding output: apply() applies the sum function to the HairEyeColor array, across all dimensions except Eye and Hair. The next line divides by the total N, to compute the proportion of the sample in each cell.



 # Sum across sex and eye
HairFreq = apply(HairEyeColor, c("Hair"), sum)            
# Marginal proportions
HairProp = HairFreq / sum(HairFreq)                        
show(round(HairProp, 2))

#Note regarding output: See previous note. Result is marginal proportions of hair colors. Notice that the proportions do not sum to 1 as should be the case due to rounding errors. 



# Sum across sex and eye
EyeFreq = apply(HairEyeColor, c("Eye"), sum)    
# Marginal proportions
EyeProp = EyeFreq / sum(EyeFreq)                           
show(round(EyeProp, 2))

#Note regarding output: See previous note. Result is marginal proportions of eye colors.



# Conditional probabilities
EyeHairProp["Blue",] / EyeProp["Blue"]                     

#Note regarding ouput: This is the "Blue" row of EyeHairProp divided by the "Blue" cell of the marginal, EyeProp. 
#The result is the conditional probability of hair color given blue eyes.
