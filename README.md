# Tracking-COVID-19


## install devtools package if it's not already
if (!requireNamespace("devtools", quietly = TRUE)) {
	
  install.packages("devtools")
}

library(devtools)


install_github("JOTAJornalismo/Tracking-COVID", ref="master")

install_github("JOTAJornalismo/Tracking-COVID", ref="master", auth_token = "ca65e068619a787afe4bbf26752c889277edfa9e")

library(TrackCOVID)




# Baixa dados da Câmara
library(tidyverse)
library(data.table)
library(TrackCOVID)


anos <- 2019::2020


df <- map_df(anos, ~{
                           fetchYearlyProposals(.x, "CD")
                           })

glimpse(df);