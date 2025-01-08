# Mental-health-diagnoses-and-facility-burden-in-the-US
# Executive summary


## Background

According to the Centers for Disease Control and Prevention (2023), more
than 1 in 5 US adults live with a mental illness. Additionally, over 1
in 5 youth aged 13-18 either currently or at some point during their
lives have experienced a seriously debilitating mental illness.
Furthermore, about 1 in 25 U.S. adults lives with a serious mental
illness, such as schizophrenia, bipolar disorder, or major depression.
However, many individuals who suffer from mental health disorders do not
receive the necessary treatment and care. In 2020, almost half of those
aged 18 and older with serious mental illness reported not receiving
treatment when needed at least once over the previous year (The White
House, 2022).

## Research Questions

Given the significant prevalence of mental illness among both adults and
youth in the United States, coupled with the concerning gap in access to
mental health treatment, this final project aims to examine four main
research questions. These include: 1) What is the distribution of mental
health facilities and clients utilizing mental health services across
the United States? 2) What is the ratio of clients with mental diagnoses
to the capacity of mental health facilities in each state? 3) Which
treatment methods are most widely utilized in mental health care within
each state? 4) What are the prevalent mental health conditions of
clients utilizing mental health services across the US?

## Datasets

We used two datasets in this final project. The 2020 National Mental
Health Services Survey (N-MHSS) was conducted from March 2020 through
November 2020. The N-MHSS collects national and state-level data from
all known facilities in the United States, both public and private, that
provide mental health treatment services to people with mental illness.
The Center for Behavioral Health Statistics and Quality (CBHSQ) of the
Substance Abuse and Mental Health Services Administration (SAMHSA), U.S.
Department of Health and Human Services, plans and directs the N-MHSS.

On the other hand, the Mental Health Client-Level Data (MH-CLD) for the
2020 reporting period provides demographic and mental health
characteristics for clients who have used mental health services in
facilities that report to individual state administrative data systems.
The general framework for the MH-CLD involves a compilation of the
demographic, clinical, and outcome data of individuals served by the
state mental health agency (SMHA) within a state-defined 12-month
reporting period. Individuals served is defined as all enrolled
individuals who received mental health and support services, including
screening, assessment, crisis services, and telemedicine/telehealth,
from programs operated or funded by the SMHA during the reporting
period.

To conduct our investigation, we used the following variables from the
MHCLD dataset: Case Identification Number (‘CASEID’); Age (‘AGE’); Sex
(‘GENDER’); Number of reported mental health diagnoses(‘NUMMHS’); State
code of reporting (‘STATEFIP’); Mental health diagnosis one (‘MH1’);
Mental health diagnosis two (‘MH2’); Mental Health diagnosis three
(‘MH3’). In addition, we also incorporated the following variables from
NMHSS: state postal code (‘LST’), facility type (‘FACILITYTYPE’), as
well as types of therapy offered by facilities(Q.A.12): individual
psychotherapy(‘TREATPSYCHOTHRPY’), couples/family
therapy(‘TREATFAMTHRPY’), group therapy(‘TREATGRPTHRPY’), cognitive
behavioral therapy(‘TREATCOGTHRPY’), dialectical behavior
therapy(‘TREATDIALTHRPY’), cognitive remediation therapy(‘TREATCOGREM’),
behavior modification(‘TREATBEHAVMOD’), integrated dual disorders
treatment(‘TREATDUALMHSA’), trauma therapy(‘TREATTRAUMATHRPY’), activity
therapy(‘TREATACTVTYTHRPY’), electroconvulsive therapy(’ TREATELECTRO’),
Transcranial Magnetic Stimulation(‘TREATTMS’), Ketamine Infusion
Therapy(‘TREATKIT’), Eye Movement Desensitization and
Reprocessing(‘TREATEMDR’), telemedicine/telehealth therapy(’
TREATTELEMEDINCE’), other mental health treatment approach(‘TREATOTH’),
none of the identified mental health treatment approaches(‘NOTREAT’).

## Dataset: mhcld2020

---------------------------------
Feature                    Result
------------------------ --------
Number of observations    6959702

Number of variables             7
---------------------------------


## Dataset: nmhss2020

---------------------------------
Feature                    Result
------------------------ --------
Number of observations      12275

Number of variables            20
---------------------------------

# Codebook summary table - mhcld2020

--------------------------------------------------------------------------------------------------------
Label   Variable                 Class         # unique  Missing   Description                          
                                                 values                                                 
------- ------------------------ ----------- ---------- ---------- -------------------------------------
        **[CASEID]**             Numeric      6959702    0.00 %    Case identification number    
        
        **[NUMMHS]**             Numeric            4    0.00 %    Number of mental health diagnoses reported    
        
        **[MH1]**                Numeric           14    0.00 %    Mental health diagnosis one                              

        **[MH2]**                Numeric           14    0.00 %   Mental health diagnosis two                            

        **[MH3]**                Numeric           14    0.00 %    Mental health diagnosis three          

        **[STATEFIP]**           Numeric           49    0.00 %    Reporting state code    

        **[LST]**                character         49    0.00 %    State Abberiviations    

        **[GENDER]**             Numeric            3    0.00 %     Sex     

        **[AGE]**                Numeric           15    0.00 %     Age (recoded)       
                                                                   
--------------------------------------------------------------------------------------------------------


# Codebook summary table - nmhss2020

--------------------------------------------------------------------------------------------------------
Label   Variable                 Class         # unique  Missing   Description                          
                                                 values                                                 
------- ------------------------ ----------- ---------- ---------- -------------------------------------
        **[CASEID]**             Numeric        12275    0.00 %    Case identification number    
        
        **[LST]**                Numeric           53    0.00 %    State Abberiviations                              

        **[FACILITYTYPE]**       Numeric           12    0.00 %   Facility type                            

        **[TREATPSYCHOTHRPY]**   Numeric            2    0.00 %    Facility offers individual psychotherapy          

        **[TREATFAMTHRPY]**      Numeric            2    0.00 %    Facility offers couples/family therapy   

        **[TREATGRPTHRPY]**      character          2    0.00 %    Facility offers group therapy    

        **[TREATCOGTHRPY]**      Numeric            2    0.00 %    Facility offers cognitive behavioral therapy     

        **[TREATDIALTHRPY]**     Numeric            2    0.00 %    Facility offers dialectical behavior therapy       

        **[TREATCOGREM]**        character          2    0.00 %    Facility provides cognitive remediation therapy
        
        **[TREATBEHAVMOD]**      character          2    0.00 %    Facility offers behavior modification
        
        **[TREATDUALMHSA]**      character          2    0.00 %    Facility offers integrated dual disorders treatment 
        
        **[TREATTRAUMATHRPY]**   character          2    0.00 %    Facility offers trauma therapy
        
        **[TREATACTVTYTHRPY]**   character          2    0.00 %    Facility offers activity therapy
        
        **[TREATELECTRO]**       character          2    0.00 %    Facility offers electroconvulsive therapy
        
        **[TREATTMS]**            Numeric           2    0.00 %    Facility provides Transcranial Magnetic Stimulation (TMS)
        
        **[TREATKIT]**            Numeric           2    0.00 %    Facility provides Ketamine Infusion Therapy (KIT)
        
        **[TREATEMDR]**           Numeric           2    0.00 %    Facility provides Eye Movement Desensitization and Reprocessing (EMDR)
        
        **[TREATTELEMEDINCE]**    Numeric           2    0.00 %    Facility offers telemedicine/telehealth therapy
        
        **[TREATOTH]**            Numeric           2    0.00 %    Facility offers other mental health treatment approach
        
        **[NOTREAT]**             Numeric           2    0.00 %    Facility offers none of the identified mental health treatment approaches
--------------------------------------------------------------------------------------------------------

# Variable list - mhcld2020

## CASEID

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type                 Numeric

Number of missing obs.        0 (0 %)

Number of unique values       6959702

-------------------------------------

## NUMMHS

-----------------------------------------------------------
Label                                                Value
----------------------------------------------- -----------
No mental health diagnoses reported                    0

One mental health diagnoses reported                   1

Two mental health diagnoses reported                   2

Three mental health diagnoses reported                 3
-----------------------------------------------------------


## Methodology

import React from 'react';
import { Card, CardHeader, CardTitle, CardContent } from '@/components/ui/card';

const MethodologyDoc = () => {
  const sections = [
    {
      title: "Data Preprocessing",
      content: [
        {
          subtitle: "Facility Type Analysis",
          details: "We filtered unnecessary rows and processed the 'FACILITYTYPE' variable, which was numerically encoded from 1 to 13 (-9 for NA values). We decoded facility names and assigned them to their respective categories, then counted different facility types across states. This data formed the basis for our circular bar graphs showing top 10 facilities by state."
        },
        {
          subtitle: "Treatment Analysis",
          details: "To represent treatment types numerically, we created 17 'state_treatment_n' subsets, each containing state postal codes and facility counts per treatment. These were merged using full-join operations into 'state_treatment', then transformed into 'long_treatment' format with columns: 'LST', 'treatments', and 'n'. This data powers our visualization of top 10 treatments by state."
        },
        {
          subtitle: "Mental Health Disease Analysis",
          details: "We analyzed variables 'MH1', 'MH2', and 'MH3' representing primary, secondary, and tertiary diagnoses. By combining these, we captured comorbidities and overall disease prevalence. The data was decoded and joined by 'LST' and 'illness_type', with counts aggregated to show disease distribution across states."
        }
      ]
    },
    {
      title: "Geographic Mapping",
      content: [
        {
          subtitle: "State Code Mapping",
          details: "We created a mapping system between state codes and abbreviations, generating tables for facility counts (state_counts_nmhss) and diagnoses (occurrences_df) by state."
        },
        {
          subtitle: "Client Diagnosis Coding",
          details: "Using 'NUMMHS' variable (0-3 range), we categorized clients based on number of diagnoses, recoding multiple diagnoses (2-3) as '1' to identify clients with any mental health diagnosis."
        },
        {
          subtitle: "Data Integration",
          details: "We merged facility and diagnosis data using 'STATE' as the join key, then integrated with US map data. The resulting table includes state names, facility counts, diagnosis counts, and facility burden calculations."
        }
      ]
    },
    {
      title: "Visualization Implementation",
      content: [
        {
          subtitle: "Interactive Choropleth",
          details: "Using leaflet package, we created an interactive map showing the distribution of clients, facilities, and facility burden across US states."
        },
        {
          subtitle: "Interactive Dashboard",
          details: "Developed circular bar charts showing facility types, treatment methods, and mental health diagnoses by state."
        },
        {
          subtitle: "Diagnosis Distribution",
          details: "Implemented plotly visualizations to show the percentage distribution of clients by number of diagnoses (0-3)."
        }
      ]
    }
  ];

  return (
    <div className="max-w-4xl mx-auto p-6 space-y-6">
      <h1 className="text-3xl font-bold text-gray-800 mb-8">Methodology</h1>
      
      {sections.map((section, idx) => (
        <Card key={idx} className="shadow-lg">
          <CardHeader>
            <CardTitle className="text-2xl text-blue-700">{section.title}</CardTitle>
          </CardHeader>
          <CardContent className="space-y-6">
            {section.content.map((item, subIdx) => (
              <div key={subIdx} className="mb-4">
                <h3 className="text-lg font-semibold text-gray-700 mb-2">{item.subtitle}</h3>
                <p className="text-gray-600 leading-relaxed">{item.details}</p >
              </div>
            ))}
          </CardContent>
        </Card>
      ))}
      
      <div className="mt-8 p-4 bg-blue-50 rounded-lg">
        <p className="text-sm text-gray-600 italic">
          This methodology document outlines our approach to analyzing and visualizing mental health facility data across the United States, including data preprocessing, geographic mapping, and interactive visualization implementation.
        </p >
      </div>
    </div>
  );
};

export default MethodologyDoc;

### Leaflet nationwide interactive choropleth

<img width="1552" alt="Screen Shot 2025-01-08 at 11 05 46" src="https://github.com/user-attachments/assets/81f2b5ac-7ffc-4282-9d80-26da074966a0" />


## Interactive circular bar chart in dashboard

![](README-1--copy_files/figure-commonmark/unnamed-chunk-2-1.png)

## Pie chart showing the comorbidity

![](README-1--copy_files/figure-commonmark/unnamed-chunk-3-1.png)

## Results

Overall, our results reveal a significant burden on mental health
facilities across the United States. Almost half of the total states
have a ratio of over 500 clients with mental health diagnoses per
facility, highlighting potential challenges for people in accessing
timely treatment. Among the states examined, New Mexico stands out with
the highest level of client burden, with a ratio of 2529.6 clients with
mental health diagnoses utilizing a single facility. Among the clients
who are using mental health facilities, 14.6% have no diagnosed mental
health condition, while 55% present with one mental health diagnosis,
23.1% with two, and 7.24% have three. These findings indicate the
complexity faced by facilities in managing clients with multiple
comorbidities. Thus, these findings highlight the disparities in client
burden across states, which emphasizes the need for targeted
interventions and resources in areas with the greatest need.
Policymakers and healthcare administrators may need to prioritize
regions with higher client-to-facility ratios to ensure equitable access
to mental healthcare services.
