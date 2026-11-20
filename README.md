# Transport Property Grids for Rocky Planet Evolution Models

This repository contains thermodynamic and transport-property grids developed for modeling the long-term thermal, orbital, and structural evolution of rocky exoplanets. These grids are designed for use in interior evolution calculations and provide material properties required to evaluate convective and conductive heat transport as well as electrical conductivity across a wide range of pressure-temperature conditions relevant to rocky planetary interiors. Accompanying Jupyter notebooks document the construction of these extensions and enable full reproduction of the published grids.

## Relation to PALEOS

The models presented here build directly upon the PALEOS framework developed by Attia et al. (2026):

> Attia, M., Lichtenberg, T., Jungová, E., & Sastre, M. (2026), *PALEOS: Multiphase Equations of State and Mass-Radius Relations for Exoplanet Interiors*, A&A, 713, A225, doi: 10.1051/0004-6361/202660790.

PALEOS provides self-consistent multiphase equations of state and interior structure calculations for rocky exoplanets. 

This repository is a complementary extension describing transport properties not included in PALEOS.

## Contents

The repository contains tabulated material properties as functions of pressure and temperature:

- Volume mass density (g/cm^3)
- Thermal expansivity (K^-1)
- Heat capacity (J/kg/K)
- Bulk modulus (GPa)
- Thermal conductivity (W/m/K)
- Electrical conductivity (S/m)
- Dynamical viscosity (Pa s)

Two distinct materials are considered: Enstatite and iron. Enstatite (MgSiO3) is the dominant silicate present in the Earth mantle and a good proxy for bulk mantle composition. We also consider pure iron (Fe) for metallic cores, ignoring any form of core pollution from lighter elements.

## Intended Applications

These grids are intended for studies of:

- Rocky exoplanet thermal evolution
- Magma-ocean cooling
- Mantle convection
- Tidal heating
- Magnetic star-planet interactions
- Interior electrical conductivity profiles
- Planetary magnetic induction calculations
- Mass-radius-interior evolution coupling

## Data Format

The transport-property tables are provided as two-dimensional grids in pressure-temperature (P-T) space.
Each physical quantity is stored as a CSV file containing the base-10 logarithm of the quantity in its native units. The grids for enstatite and iron can be found in the "EOS_data" folder.

The repository additionally provides:

- P_range : pressure grid values corresponding to the rows of the tabulated data.
- T_range : temperature grid values corresponding to the columns of the tabulated data.
- 
Together, each CSV file and its associated P_range and T_range arrays define a regular two-dimensional grid. Interpolation between grid points may be performed directly in logarithmic space or after conversion back to physical units, depending on the requirements of the application.

## Reproducing the Grids

In addition to the tabulated datasets, this repository provides a Jupyter notebook (Transport_properties_gris.ipynb) that documents the construction of the transport-property extensions to the PALEOS framework.
The notebook contains the methodology used to generate the transport-property grids presented in this repository, including:

- Thermal conductivity
- Electrical conductivity
- Viscosity
  
The notebook is intended as a transparent and reproducible companion to the tabulated data products. Users may employ it to regenerate the grids, modify assumptions, or extend/improve the calculations to additional parameter ranges.
Only the transport-property calculations are included here. For the construction of the underlying thermodynamic and equation-of-state (EOS) grids, including phase equilibria and other interior properties, readers are referred to Attia et al. (2026), who present the original PALEOS framework and describe the generation of those fundamental datasets.
The notebook additionally reproduces Figures 2 and 3 of Savignac & Lee (2026), which illustrate the construction and validation of the transport-property grids. These figures provide a visual overview of the methodology and resulting parameter-space coverage.

## Citation

If you use these grids in published work, please cite both the original PALEOS publication and Savignac & Lee (2026).

### PALEOS

> Attia, M., Lichtenberg, T., Jungová, E., & Sastre, M. (2026), *PALEOS: Multiphase Equations of State and Mass-Radius Relations for Exoplanet Interiors*, A&A, 713, A225, doi: 10.1051/0004-6361/202660790.

Available at: [10.1051/0004-6361/202660790](https://www.aanda.org/articles/aa/full_html/2026/09/aa60790-26/aa60790-26.html)

### The Electromagnetic Life and Death of Ultra-Short-Period Planets

ADD CITATION

## Disclaimer

These grids are provided for research purposes. While extensive validation has been performed, users are encouraged to verify that the adopted parameter space, material assumptions, and interpolation methods are appropriate for their specific application.
