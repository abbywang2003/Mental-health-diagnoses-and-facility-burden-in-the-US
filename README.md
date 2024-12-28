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

## Methodology

In our methodology, we began by filtering out unnecessary rows from the
dataset. Next, we focused on the variable ‘FACILITYTYPE’ and computed
the count of facilities using each treatment category within every
class. Since ‘FACILITYTYPE’ is encoded numerically from 1 to 13, with
‘-9’ representing NA values, we decoded the facility names and assigned
them to their respective numeric categories within ‘FACILITYTYPE’. We
count different facility types in different states. Using these data, we
plotted a circular bar graph for different states, showing the top 10
facilities built in each states.

To streamline our analysis, we aimed to represent each treatment type
numerically and tally the number of facilities employing each treatment.
However, in the original dataset, treatments were encoded as separate
variables. To address this, we created 17 subsets named
“state_treatment_n”, where each subset corresponds to a specific
treatment. Each of these subsets comprises two columns, representing the
state postal code and the number of facilities using this treatment in
each state.

Then, by merging these subsets through a full-join operation, we
constructed a comprehensive dataset named ‘state_treatment’ with three
columns: ‘LST’, each treatment, and the count of each treatment. Each
row in this dataset represents a state along with its corresponding
treatment counts. Subsequently, we reshaped the ‘state_treatment’
dataset into a longer format, creating a new dataset named
“long_treatment”. Following column renaming and data cleansing
procedures, the ‘long_treatment’ dataset now comprises three columns:
“LST”, “treatments”, and “n”. This refined dataset offers a succinct
overview of treatment frequencies across states. Using these data, we
also plotted a circular bar graph for different states, showing the top
10 treatment utilize in facilities in each states.

Also, to look into the prevalence of different mental health diseases in
different states, we focused on variables “MH1”, “MH2”, and “MH3”, which
indicate the client’s first, second and third diagnosis respectively.
The presence of second and third diagnoses signifies the existence of
comorbidities.To compute the disease prevalence, we added up the
occurence of MH1, MH2, and MH3, to compile all the diagnoses of
different mental health diseases. To accomplish this goal, we decoded
MH1, MH2, and MH3 and full-joined them by “LST” and “illness_type”.
Then, we add up the count of MH1, MH2, MH3 correspondingly. Using these
data, we plotted a circular bar graph for different states, showing the
top 10 prevalence of mental health diseases in each state.

Additionally, we create a mapping between state codes and their
abbreviations. Following this, we generated a table of counts for mental
health service facilities (state_counts_nmhss) and another table for
mental health diagnoses (occurrences_df), which represent the counts of
facilities and diagnoses per state, respectively. Here, the count of
clients diagnosed with mental health issues was determined by coding
individuals according to the variable ‘NUMMHS,’ which denotes the number
of reported mental health diagnoses. This variable is categorical, with
values ranging from “0” to “3” representing the absence of diagnosis or
the presence of one, two, or three diagnoses, respectively. To
distinguish clients with mental health diagnoses from those without, we
recoded values “2” and “3” as “1.”

Subsequently, we merged the two data frames utilizing the variable
‘STATE’ as the join key. Then, as we prepared to create a map of the
United States using the us_map function, we joined this map data with
the merged data table (merged_data1). After cleaning up table column
names, the updated output table (merged_data2) comprises columns listing
the state names, the total number of facilities within each state, the
count of clients diagnosed with at least one disorder, and the facility
burden. The facility burden is computed by dividing the number of
clients diagnosed with at least one disorder by the total number of
mental health facilities in each state.

Regarding data visualization, using the resulting data frame (new), we
utilized the ‘leaflet’ package to generate an interactive choropleth
illustrating the distribution of clients with mental disorders, the
number of facilities, and the facility burden across different states in
the US. Furthermore, we developed an interactive dashboard with three
circular bar charts, to present, respectively, the types of facilities
utilized in each state, the top treatment methods employed in each state
using an interactive bar chart, and the top mental health diagnoses
prevalent in each state. Also, to visualize the distribution of clients
based on the number of mental health diagnoses, we utilized the ‘plotly’
package to depict the percentage of clients with zero, one, two, and
three diagnoses.

### Leaflet nationwide interactive choropleth

![](README-1--copy_files/figure-commonmark/unnamed-chunk-1-1.png)

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
