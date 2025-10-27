PDS4 LCROSS Mission Data Dictionary User's Guide  
[Last edited](#edit-history): 2025-10-24  
  
# Introduction  
1. Purpose of this User's Guide  
    - This User's Guide provides an overview of the LCROSS Mission Data Dictionary. The guide details how to include the dictionary in a PDS4 label, describes the organization of the dictionary's classes and attributes, provides definitions for these classes and attributes, and lists example excerpts from labels that use them.  
2. Audience  
    - This User's Guide should be useful to data providers intending to archive LCROSS data with PDS as well as PDS Nodes who are working with these data providers.  
  
# Overview of the LCROSS Mission Data Dictionary  
The LCROSS Mission Data Dictionary contains classes and attributes specific to the LCROSS mission and its instruments.  
Steward: Jennifer Ward, PDS Geosciences Node, jgward@wustl.edu  
  
# Document Outline  
1. [How to Include the LCROSS Mission Data Dictionary in a PDS4 Label](#how-to-include-the-LCROSS-Mission-data-dictionary-in-a-pds4-label)  
2. [Organization of Classes and Attributes](#organization-of-classes-and-attributes)  
    1. [Class Organization](#class-organization)  
    2. [Attributes by Class](#attributes-by-class)  
3. [Definitions](#definitions)  
    1. [Classes (in alphabetical order)](#classes-in-alphabetical-order)  
    2. [Attributes (in alphabetical order)](#attributes-in-alphabetical-order)  
4. [Examples](#examples)  
5. [Edit History](#edit-history)  
  
# How to Include the LCROSS Mission Data Dictionary in a PDS4 Label  
The dictionary consists of a set of files with names in the form PDS4_LCROSS_xxxx_yyyy.ext, where  
- xxxx = the PDS4 Information Model version, e.g. 1E00  
- yyyy = the LCROSS Mission Data Dictionary version, e.g. 1100  
  
and the file extensions are  
  
- .csv = A comma-separated value table of dictionary attributes  
- .JSON = The dictionary contents in JSON format  
- .sch = The dictionary "rules" as an XML Schematron file  
- .txt = The report generated when the dictionary was built  
- .xml = The PDS4 label that describes this set of files  
- .xsd = The dictionary contents as an XML schema file  
  
Only the schema and Schematron files are needed for validating a PDS4 label.  
  
The latest version of this dictionary may be found on the PDS web site at https://pds.nasa.gov/datastandards/dictionaries/index-missions.shtml#lcross.  
  
The following is an example showing the use of this dictionary in a PDS4 label.  
  
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1E00.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<?xml-model href="https://pds.nasa.gov/pds4/mission/lcross/v1/PDS4_LCROSS_1E00_1100.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<Product_Observational xmlns="http://pds.nasa.gov/pds4/pds/v1"
    xmlns:lcross="http://pds.nasa.gov/pds4/mission/lcross/v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1E00.xsd
                        https://pds.nasa.gov/pds4/mission/lcross/v1/PDS4_LCROSS_1E00_1100.xsd">
```  
  
The following is a schematic example showing the location of every LCROSS Mission Data Dictionary class and attribute in a PDS4 label. Note that not all classes and attributes may be mutually compatible, and the example does not include any recursion, even if recursion is allowed.  
```
<Observation_Area>
  ...
  <Mission_Area>
    <lcross:LCROSS_Parameters>
      <lcross:Mission_Parameters>
        <lcross:product_type/>
        <lcross:producer_name/>
        <lcross:producer_institution_name/>
        <lcross:mission_phase_name/>
        <lcross:spacecraft_clock_start_count/>
        <lcross:spacecraft_clock_stop_count/>
        <lcross:intercept_point_latitude/>
        <lcross:intercept_point_longitude/>
        <lcross:instrument_temperature/>
        <lcross:instrument_temperature_count/>
      </lcross:Mission_Parameters>
      <lcross:MIR_Instrument_State>
        <lcross:instrument_gain_state/>
        <lcross:missing_packet_flag/>
        <lcross:calibration_valid/>
      </lcross:MIR_Instrument_State>
      <lcross:NIR_Instrument_State>
        <lcross:enhancement_mode/>
        <lcross:operating_setting_value/>
        <lcross:integration_time/>
        <lcross:gain_value/>
      </lcross:NIR_Instrument_State>
      <lcross:NSP_Instrument_State>
        <lcross:saturation_flag/>
        <lcross:boresight_to_sun_angle/>
      </lcross:NSP_Instrument_State>
      <lcross:VSP_Instrument_State>
        <lcross:saturation_flag/>
        <lcross:exposure_duration/>
        <lcross:tec_setpoint/>
        <lcross:tec_temperature/>
        <lcross:packet_timestamp/>
        <lcross:vsp_bracket_number/>
      </lcross:VSP_Instrument_State>
      <lcross:Ground_Based_Parameters>
        <lcross:right_ascension_angle/>
        <lcross:declination/>
        <lcross:exposure_length/>
        <lcross:filter_name/>
        <lcross:center_filter_wavelength/>
      </lcross:Ground_Based_Parameters>
    </lcross:LCROSS_Parameters>
  </Mission_Area>
  ...
</Observation_Area>
```  
  
The namespace for the LCROSS Mission Data Dictionary is http://pds.nasa.gov/pds4/mission/lcross/v1, abbreviated "lcross:".  
  
# Organization of Classes and Attributes  
  
## Class Organization  
Below is a structured list showing the organization of classes, ordered by appearance in the PDS4 label. Each class name is linked to its complete definition in the [Definitions](#definitions) section.  
- [LCROSS_Parameters](#lcross_parameters)  
  - [Mission_Parameters](#mission_parameters)  
  - [MIR_Instrument_State](#mir_instrument_state)  
  - [NIR_Instrument_State](#nir_instrument_state)  
  - [NSP_Instrument_State](#nsp_instrument_state)  
  - [VSP_Instrument_State](#vsp_instrument_state)  
  - [Ground_Based_Parameters](#ground_based_parameters)  
  
## Attributes by Class  
The attributes immediately under each class (if any) are listed below. Both classes and attributes are ordered by appearance in the PDS4 label; however, each class is listed only once, even if that class can appear in more than one place in a PDS4 label. Each class and attribute name is linked to its complete definition in the [Definitions](#definitions) section.  
  
### [LCROSS_Parameters](#lcross_parameters) (attribute list)  
  
### [Mission_Parameters](#mission_parameters) (attribute list)  
- [product_type](#product_type)  
- [producer_name](#producer_name)  
- [producer_institution_name](#producer_institution_name)  
- [mission_phase_name](#mission_phase_name)  
- [spacecraft_clock_start_count](#spacecraft_clock_start_count)  
- [spacecraft_clock_stop_count](#spacecraft_clock_stop_count)  
- [intercept_point_latitude](#intercept_point_latitude)  
- [intercept_point_longitude](#intercept_point_longitude)  
- [instrument_temperature](#instrument_temperature)  
- [instrument_temperature_count](#instrument_temperature_count)  
  
### [MIR_Instrument_State](#mir_instrument_state) (attribute list)  
- [instrument_gain_state](#instrument_gain_state)  
- [missing_packet_flag](#missing_packet_flag)  
- [calibration_valid](#calibration_valid)  
  
### [NIR_Instrument_State](#nir_instrument_state) (attribute list)  
- [enhancement_mode](#enhancement_mode)  
- [operating_setting_value](#operating_setting_value)  
- [integration_time](#integration_time)  
- [gain_value](#gain_value)  
  
### [NSP_Instrument_State](#nsp_instrument_state) (attribute list)  
- [saturation_flag](#saturation_flag)  
- [boresight_to_sun_angle](#boresight_to_sun_angle)  
  
### [VSP_Instrument_State](#vsp_instrument_state) (attribute list)  
- [saturation_flag](#saturation_flag)  
- [exposure_duration](#exposure_duration)  
- [tec_setpoint](#tec_setpoint)  
- [tec_temperature](#tec_temperature)  
- [packet_timestamp](#packet_timestamp)  
- [vsp_bracket_number](#vsp_bracket_number)  
  
### [Ground_Based_Parameters](#ground_based_parameters) (attribute list)  
- [right_ascension_angle](#right_ascension_angle)  
- [declination](#declination)  
- [exposure_length](#exposure_length)  
- [filter_name](#filter_name)  
- [center_filter_wavelength](#center_filter_wavelength)  
  
# Definitions  
  
## Classes (in alphabetical order)  
  
### Ground_Based_Parameters  
Container class for ground-based observation parameters.  
- [go to attribute list](#ground_based_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### LCROSS_Parameters  
Top level container class.  
- [go to attribute list](#lcross_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### MIR_Instrument_State  
Class with attributes specific to the MIR instrument on LCROSS.  
- [go to attribute list](#mir_instrument_state-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Mission_Parameters  
Container class for mission level attributes (i.e., common across all or most instruments) and instrument specific classes.  
- [go to attribute list](#mission_parameters-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### NIR_Instrument_State  
Class with attributes specific to the NIR instrument on LCROSS.  
- [go to attribute list](#nir_instrument_state-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### NSP_Instrument_State  
Class with attributes specific to the NSP instrument on LCROSS.  
- [go to attribute list](#nsp_instrument_state-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### VSP_Instrument_State  
Class with attributes specific to the VSP instrument on LCROSS.  
- [go to attribute list](#vsp_instrument_state-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
## Attributes (in alphabetical order)  
  
### *boresight_to_sun_angle*  
Angle between the instrument boresight vector and the spacecraft to sun vector in degrees.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *calibration_valid*  
The response of the mid-IR cameras exhibited a startup transient. The calibration is valid only after this transient had settled. This attribute indicates whether the image was taken before or after this point. Values are Yes or No.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - No  
    - Description: Calibration is not valid.  
  - Yes  
    - Description: Calibration is valid.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *center_filter_wavelength*  
The center wavelength of a filter used in an imaging system.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *declination*  
The declination_angle (Dec) attribute provides the value of an angle on the celestial sphere, measured north from the celestial equator to the point in question. (For points south of the celestial equator, negative values are used.) Declination is used in conjunction with right ascension (right_ascension_angle) to specify a point on the sky.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *enhancement_mode*  
This attribute indicates whether onboard image stretching was enabled or disabled. Values are On or Off.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Off  
    - Description: Onboard image enhancement was disabled.  
  - On  
    - Description: Onboard image enhancement was enabled.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_duration*  
The time interval between the opening and closing of an instrument aperture.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *exposure_length*  
Provides the length of time for an exposure.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *filter_name*  
The commonly used name of a filter the is part of an imaging system.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *gain_value*  
The focal plane sensitivity in electrons per count. Value is approximate and inferred from the operating setting value and factory definitions.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *instrument_gain_state*  
The instrument_gain_state specifies the instrument gain state, either High or Low.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - High  
    - Description: High  
  - Low  
    - Description: Low  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *instrument_temperature*  
The instrument_temperature attribute provides the temperature, in degrees Celsius of an instrument or some part of an instrument.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *instrument_temperature_count*  
The instrument_temperature_count attribute provides the temperature of an instrument in raw counts or DN values.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *integration_time*  
The integration time in msec.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *intercept_point_latitude*  
The intercept_point_latitude attribute is the latitude of a point on the surface of a body.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90.0  
- Maximum value: 90.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *intercept_point_longitude*  
The intercept_point_longitude attribute is the longitude of a point on the surface of a body.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *missing_packet_flag*  
The missing_packet_flag indicates whether the image is missing data. A missing packet appears as a horizontal bar 8 pixels high of zero data.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - No  
    - Description: No packets were missed.  
  - Yes  
    - Description: Packets are missing.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *mission_phase_name*  
 The mission_phase_name element provides the commonly-used identifier of a mission phase.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Earthlook1  
    - Description: Earthlook1  
  - Earthlook2  
    - Description: Earthlook2  
  - Impact  
    - Description: Impact  
  - Mirlook  
    - Description: Mirlook  
  - Preimpact  
    - Description: Preimpact  
  - Quicklook  
    - Description: Quicklook  
  - Separation  
    - Description: Separation  
  - Starfield  
    - Description: Starfield  
  - Swingby  
    - Description: Swingby  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *operating_setting_value*  
The operating setting value determines the integration time and gain. Values range from 0 to 15.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 15  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *packet_timestamp*  
A 32-bit unsigned integer representing time from the epoch Jan 1, 1980 in milliseconds. This counter resets every approximately 50 days.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *producer_institution_name*  
 The producer_institution_name element identifies a university, research center, NASA center or other institution associated with the production of a data set.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *producer_name*  
The name of the person who produced the data product.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *product_type*  
 The product_type attributes identifies the type or category of a product within a data set.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Calibrated Data  
    - Description: Calibrated data from an instrument.  
  - Calibrated Image  
    - Description: A radiometrically calibrated image product.  
  - Calibrated Spectrum  
    - Description: A radiometrically calibrated spectrum product.  
  - Raw Data  
    - Description: Raw output from an instrument, usually in DN.  
  - Raw Image  
    - Description: A raw image product.  
  - Raw Spectrum  
    - Description: A raw spectrum product.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *right_ascension_angle*  
The right_ascension_angle attribute provides the value of right ascension (RA) as an angle. Right ascension is measured from the vernal equinox or the first point of Aries, which is the place on the celestial sphere where the Sun crosses the celestial equator from south to north at the March equinox. Right ascension is measured continuously in a full circle from that equinox towards the east. Right ascension is used in conjunction with the declination attribute to specify a point on the sky.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *saturation_flag*  
Indicates whether a spectra is saturated based on a mechanical test.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - No  
    - Description: No saturation.  
  - Yes  
    - Description: Saturation noted.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spacecraft_clock_start_count*  
The spacecraft_clock_start_count attribute provides the value of the spacecraft clock at the beginning of a time period of interest.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 15  
- Maximum Length: 15  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spacecraft_clock_stop_count*  
The spacecraft_clock_stop_count attribute provides the value of the spacecraft clock at the end of a time period of interest.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tec_setpoint*  
The setpoint temperature of the VSP thermo-electric cooler.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *tec_temperature*  
The measurement temperature of the VSP thermo-electric cooler.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *vsp_bracket_number*  
When in bracket mode, the VSP captures three spectra in quick succession. The bracket number indicates which of the three spectra are captured..  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
# Examples  
  
Example PDS4 label snippet from urn:nasa:pds:lcross_impactor:data_vsp:lcross_vsp_cal_20090801215147874::1.0:  
```
<Mission_Area>
  <lcross:LCROSS_Parameters>
    <lcross:Mission_Parameters>
      <lcross:product_type>Calibrated Spectrum</lcross:product_type>
      <lcross:producer_institution_name>Ames Research Center</lcross:producer_institution_name>
      <lcross:mission_phase_name>Earthlook1</lcross:mission_phase_name>
      <lcross:spacecraft_clock_start_count>000001830997374</lcross:spacecraft_clock_start_count>
      <lcross:spacecraft_clock_stop_count>000001830997874</lcross:spacecraft_clock_stop_count>
      <lcross:instrument_temperature unit="degC">14.18</lcross:instrument_temperature>
      <lcross:instrument_temperature_count>3272</lcross:instrument_temperature_count>
    </lcross:Mission_Parameters>
    <lcross:VSP_Instrument_State>
      <lcross:saturation_flag>No</lcross:saturation_flag>
      <lcross:exposure_duration>0.500</lcross:exposure_duration>
      <lcross:tec_setpoint unit="degC">-10.00</lcross:tec_setpoint>
      <lcross:tec_temperature unit="degC">18.10</lcross:tec_temperature>
      <lcross:packet_timestamp>1831000488</lcross:packet_timestamp>
      <lcross:vsp_bracket_number>1</lcross:vsp_bracket_number>
    </lcross:VSP_Instrument_State>
  </lcross:LCROSS_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:lcross_mro_photdoc:data:20091009d_018::1.0:  
```
<Mission_Area>
  <lcross:LCROSS_Parameters>
    <lcross:Mission_Parameters>
      <lcross:product_type>Raw Image</lcross:product_type>
      <lcross:producer_name>Marc W. Buie</lcross:producer_name>
      <lcross:producer_institution_name>Southwest Research Institute</lcross:producer_institution_name>
    </lcross:Mission_Parameters>
    <lcross:Ground_Based_Parameters>
      <lcross:right_ascension_angle unit="deg">79.10625</lcross:right_ascension_angle>
      <lcross:declination unit="deg">21.82306</lcross:declination>
      <lcross:exposure_length unit="s">20.000</lcross:exposure_length>
      <lcross:filter_name>D-RED</lcross:filter_name>
      <lcross:center_filter_wavelength unit="micrometer">0.7620</lcross:center_filter_wavelength>
    </lcross:Ground_Based_Parameters>
  </lcross:LCROSS_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:lcross_impactor:data_mir1:lcross_mir1_cal_20090623121825483::1.0:  
```
<Mission_Area>
  <lcross:LCROSS_Parameters>
    <lcross:Mission_Parameters>
      <lcross:product_type>Calibrated Image</lcross:product_type>
      <lcross:producer_institution_name>Ames Research Center</lcross:producer_institution_name>
      <lcross:mission_phase_name>Swingby</lcross:mission_phase_name>
      <lcross:spacecraft_clock_start_count>000002721962450</lcross:spacecraft_clock_start_count>
      <lcross:spacecraft_clock_stop_count>000002721962483</lcross:spacecraft_clock_stop_count>
      <lcross:intercept_point_latitude unit="deg">1.261</lcross:intercept_point_latitude>
      <lcross:intercept_point_longitude unit="deg">142.657</lcross:intercept_point_longitude>
      <lcross:instrument_temperature unit="degC">17.36</lcross:instrument_temperature>
      <lcross:instrument_temperature_count>3175</lcross:instrument_temperature_count>
    </lcross:Mission_Parameters>
    <lcross:MIR_Instrument_State>
      <lcross:instrument_gain_state>High</lcross:instrument_gain_state>
      <lcross:missing_packet_flag>No</lcross:missing_packet_flag>
      <lcross:calibration_valid>No</lcross:calibration_valid>
    </lcross:MIR_Instrument_State>
  </lcross:LCROSS_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:lcross_impactor:data_nir2:lcross_nir2_cal_20090801215055936::1.0:  
```
<Mission_Area>
  <lcross:LCROSS_Parameters>
    <lcross:Mission_Parameters>
      <lcross:product_type>Calibrated Image</lcross:product_type>
      <lcross:producer_institution_name>Ames Research Center</lcross:producer_institution_name>
      <lcross:mission_phase_name>Earthlook1</lcross:mission_phase_name>
      <lcross:spacecraft_clock_start_count>000001830945936</lcross:spacecraft_clock_start_count>
      <lcross:spacecraft_clock_stop_count>000001830945936</lcross:spacecraft_clock_stop_count>
      <lcross:instrument_temperature unit="degC">21.88</lcross:instrument_temperature>
      <lcross:instrument_temperature_count>3033</lcross:instrument_temperature_count>
    </lcross:Mission_Parameters>
    <lcross:NIR_Instrument_State>
      <lcross:enhancement_mode>Off</lcross:enhancement_mode>
      <lcross:operating_setting_value>6</lcross:operating_setting_value>
      <lcross:integration_time unit="ms">830</lcross:integration_time>
      <lcross:gain_value>1400</lcross:gain_value>
    </lcross:NIR_Instrument_State>
  </lcross:LCROSS_Parameters>
</Mission_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:lcross_impactor:data_nsp2:lcross_nsp2_raw_20091009113023969::1.0:  
```
<Mission_Area>
  <lcross:LCROSS_Parameters>
    <lcross:Mission_Parameters>
      <lcross:product_type>Raw Spectrum</lcross:product_type>
      <lcross:producer_institution_name>Ames Research Center</lcross:producer_institution_name>
      <lcross:mission_phase_name>Impact</lcross:mission_phase_name>
      <lcross:spacecraft_clock_start_count>000003460346546</lcross:spacecraft_clock_start_count>
      <lcross:spacecraft_clock_stop_count>000003460347046</lcross:spacecraft_clock_stop_count>
      <lcross:instrument_temperature unit="degC">15.64</lcross:instrument_temperature>
      <lcross:instrument_temperature_count>3228</lcross:instrument_temperature_count>
    </lcross:Mission_Parameters>
    <lcross:NSP_Instrument_State>
      <lcross:saturation_flag>No</lcross:saturation_flag>
      <lcross:boresight_to_sun_angle unit="deg">15.313</lcross:boresight_to_sun_angle>
    </lcross:NSP_Instrument_State>
  </lcross:LCROSS_Parameters>
</Mission_Area>
```  
  
# Edit History  
*See also: [LCROSS change log](https://github.com/pds-data-dictionaries/ldd-lcross/blob/main/CHANGELOG.md).*  
2025-10-24  Jennifer Ward  
