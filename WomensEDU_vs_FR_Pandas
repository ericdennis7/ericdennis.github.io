#Eric Dennis
#Last Update: April 19th, 2023
#Project: The Impact of Education on Women's Fertility Rates (Globally)
#Program Explanation: This program takes data from a CSV file and cleans it using pandas.
#                     It also calculates various statistics such as averages and group by's.

#Imports
import pandas as pd
import plotly.graph_objects as go


#Setting pandas rules to allow all the rows and columns to print out without restriction.
pd.set_option('display.max_rows', None)
pd.set_option('display.max_columns', None)


#Connecting to the CSV file using pandas.
data = pd.read_csv("C:\\Users\\ericd\\Downloads\\womens-educational-attainment-vs-fertility.csv")


#Listing the countries that are present in 2010 according to AI and removing them if they are not.
countries = ['Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Antigua and Barbuda', 'Argentina', 'Armenia', 'Australia', 'Austria', 'Azerbaijan', 'Bahamas', 'Bahrain', 'Bangladesh', 'Barbados', 'Belarus', 'Belgium', 'Belize', 'Benin', 'Bhutan', 'Bolivia', 'Bosnia and Herzegovina', 'Botswana', 'Brazil', 'Brunei', 'Bulgaria', 'Burkina Faso', 'Burundi', 'Cabo Verde', 'Cambodia', 'Cameroon', 'Canada', 'Central African Republic', 'Chad', 'Chile', 'China', 'Colombia', 'Comoros', 'Costa Rica', "Côte d'Ivoire", 'Croatia', 'Cuba', 'Cyprus', 'Czech Republic', 'Democratic Republic of the Congo', 'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic', 'East Timor', 'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Estonia', 'Eswatini', 'Ethiopia', 'Fiji', 'Finland', 'France', 'Gabon', 'Gambia', 'Georgia', 'Germany', 'Ghana', 'Greece', 'Grenada', 'Guatemala', 'Guinea', 'Guinea-Bissau', 'Guyana', 'Haiti', 'Honduras', 'Hungary', 'Iceland', 'India', 'Indonesia', 'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy', 'Jamaica', 'Japan', 'Jordan', 'Kazakhstan', 'Kenya', 'Kiribati', 'Kosovo', 'Kuwait', 'Kyrgyzstan', 'Laos', 'Latvia', 'Lebanon', 'Lesotho', 'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg', 'Madagascar', 'Malawi', 'Malaysia', 'Maldives', 'Mali', 'Malta', 'Marshall Islands', 'Mauritania', 'Mauritius', 'Mexico', 'Micronesia', 'Moldova', 'Monaco', 'Mongolia', 'Montenegro', 'Morocco', 'Mozambique', 'Myanmar', 'Namibia', 'Nauru', 'Nepal', 'Netherlands', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria', 'North Korea', 'North Macedonia', 'Northern Cyprus', 'Norway', 'Oman', 'Pakistan', 'Palau', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 'Philippines', 'Poland', 'Portugal', 'Qatar', 'Republic of the Congo', 'Romania', 'Russia', 'Rwanda', 'Saint Kitts and Nevis', 'Saint Lucia', 'Saint Vincent and the Grenadines', 'Samoa', 'San Marino', 'São Tomé and Príncipe', 'Saudi Arabia', 'Senegal', 'Serbia', 'Seychelles', 'Sierra Leone', 'Singapore', 'Slovakia', 'Slovenia', 'Solomon Islands', 'Somalia', 'South Africa', 'South Korea', 'South Sudan', 'Spain', 'Sri Lanka', 'Sudan', 'Suriname', 'Svalbard and Jan Mayen', 'Sweden', 'Switzerland', 'Syria', 'Taiwan', 'Tajikistan', 'Tanzania', 'Thailand', 'Timor-Leste', 'Togo', 'Tokelau', 'Tonga', 'Trinidad and Tobago', 'Tunisia', 'Turkey', 'Turkmenistan', 'Turks and Caicos Islands', 'Tuvalu', 'Uganda', 'Ukraine', 'United Arab Emirates', 'United Kingdom', 'United States', 'Uruguay', 'Uzbekistan', 'Vanuatu', 'Vatican', 'Venezuela', 'Vietnam', 'Wallis and Futuna', 'Western Sahara', 'Yemen', 'Zambia', 'Zimbabwe', 'Åland Islands'
            ]

data = data[data['Entity'].isin(countries)]

#Renaming columns to shorter names for readability.
data = data.rename(columns={"Estimates, 1950 - 2020: Annually interpolated demographic indicators - Total fertility (live births per woman)": "Fertility_Rate", 
                            "Mean years of schooling, women (in reproductive age 15 to 49) (Our World In Data (2017))":"Years_of_Education"})


#Applying the new data that lists each countries population, fertility rate, and education level in the existing CSV file.
data.to_csv("C:\\Users\\ericd\\Desktop\\womens-educational-attainment-vs-fertility.csv", index=False)

#Getting the average fertility rate per year using a groupby and .mean in pandas, dropping NaN values, and rounding values to 2.
yearly_fer_and_edu = data.groupby("Year")[["Fertility_Rate", "Years_of_Education"]].mean().reset_index().rename(columns = {"Year": "Year", "Fertility_Rate": "Fertility_Rate"})
yearly_fer_and_edu = yearly_fer_and_edu.loc[(yearly_fer_and_edu["Year"] >= 1950) & (yearly_fer_and_edu['Year'] <= 2010)]
yearly_fer_and_edu = yearly_fer_and_edu.round(2)

yearly_fer_and_edu.to_csv("C:\\Users\\ericd\\Desktop\\groupby_year_womensedu_vs_womensfr.csv", index=False)
