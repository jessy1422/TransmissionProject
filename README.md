# TransmissionProject
# -*- coding: utf-8 -*-
"""
Created on Sun May 28 18:32:20 2023

@author: jessi
"""

def get_number_of_cells(city_size, numOfPPL, number_of_calls_per_user, average_call_duration, number_of_channels, maximum_number_of_channels_per_base_station, sectoring_level):

  # Calculate the number of users in the city.
  number_of_users = city_size * numOfPPL

  # Calculate the number of channels required to support the number of users.
  number_of_channels_required = number_of_users * (number_of_calls_per_user * average_call_duration) / 60

  # Calculate the number of base stations required.
  number_of_base_stations = number_of_channels_required / maximum_number_of_channels_per_base_station

  # Calculate the number of cells required.
  number_of_cells = number_of_base_stations * sectoring_level

  return number_of_cells

numOfCells = get_number_of_cells(100, 100, 100, 1, 100, 10, 60)
