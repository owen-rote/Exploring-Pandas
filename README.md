### Exploring Pandas
**[github.com/owen-rote](https://github.com/owen-rote)** 
**Purpose:** This notebook demonstrates basic functionalities of the Pandas Python library for Data Science and statistics. This notebook covers topics such as reading and writing files, sorting data, editing data, filtering data, and more.

## Followed: [Tutorial by freeCodeCamp.org on Youtube](https://www.youtube.com/watch?v=vmEHCJofslg)

### Loading data with Pandas


```python
import pandas as pd

# Load dataframe
df = pd.read_csv('pokemon_data.csv')
# We can also use: pd.read_excel() & pd.read_csv(delimiter='\t')

print(df.head(3))
```

       #       Name Type 1  Type 2  HP  Attack  Defense  Sp. Atk  Sp. Def  Speed  \
    0  1  Bulbasaur  Grass  Poison  45      49       49       65       65     45   
    1  2    Ivysaur  Grass  Poison  60      62       63       80       80     60   
    2  3   Venusaur  Grass  Poison  80      82       83      100      100     80   
    
       Generation  Legendary  
    0           1      False  
    1           1      False  
    2           1      False  
    

### Reading Data in Pandas


```python
# Read Headers
df.columns

# Read each of a column
#print(df[['Name', 'Type 1', 'HP']])
#print(df['Name'])


# Read each row
# print(df.iloc[1])
# for index, row in df.iterrows():
#     print(index, row['Name'])
df.loc[df['Type 1'] == 'Grass'] # Locates all entries with Type 1 == Fire
# Read specific location (R, C)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Bulbasaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>45</td>
      <td>49</td>
      <td>49</td>
      <td>65</td>
      <td>65</td>
      <td>45</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Ivysaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>60</td>
      <td>62</td>
      <td>63</td>
      <td>80</td>
      <td>80</td>
      <td>60</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>82</td>
      <td>83</td>
      <td>100</td>
      <td>100</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>VenusaurMega Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>100</td>
      <td>123</td>
      <td>122</td>
      <td>120</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>48</th>
      <td>43</td>
      <td>Oddish</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>45</td>
      <td>50</td>
      <td>55</td>
      <td>75</td>
      <td>65</td>
      <td>30</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>718</th>
      <td>650</td>
      <td>Chespin</td>
      <td>Grass</td>
      <td>NaN</td>
      <td>56</td>
      <td>61</td>
      <td>65</td>
      <td>48</td>
      <td>45</td>
      <td>38</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>719</th>
      <td>651</td>
      <td>Quilladin</td>
      <td>Grass</td>
      <td>NaN</td>
      <td>61</td>
      <td>78</td>
      <td>95</td>
      <td>56</td>
      <td>58</td>
      <td>57</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>720</th>
      <td>652</td>
      <td>Chesnaught</td>
      <td>Grass</td>
      <td>Fighting</td>
      <td>88</td>
      <td>107</td>
      <td>122</td>
      <td>74</td>
      <td>75</td>
      <td>64</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>740</th>
      <td>672</td>
      <td>Skiddo</td>
      <td>Grass</td>
      <td>NaN</td>
      <td>66</td>
      <td>65</td>
      <td>48</td>
      <td>62</td>
      <td>57</td>
      <td>52</td>
      <td>6</td>
      <td>False</td>
    </tr>
    <tr>
      <th>741</th>
      <td>673</td>
      <td>Gogoat</td>
      <td>Grass</td>
      <td>NaN</td>
      <td>123</td>
      <td>100</td>
      <td>62</td>
      <td>97</td>
      <td>81</td>
      <td>68</td>
      <td>6</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>70 rows × 12 columns</p>
</div>



### Sorting/Describing Data


```python
# Get a rundown of the data
print(df.describe())

#df.sort_values('Name')
# Sort by type, then HP with Type ascending and HP descending
df.sort_values(['Type 1', 'HP'], ascending=[1, 0])
```

                    #          HP      Attack     Defense     Sp. Atk     Sp. Def  \
    count  800.000000  800.000000  800.000000  800.000000  800.000000  800.000000   
    mean   362.813750   69.258750   79.001250   73.842500   72.820000   71.902500   
    std    208.343798   25.534669   32.457366   31.183501   32.722294   27.828916   
    min      1.000000    1.000000    5.000000    5.000000   10.000000   20.000000   
    25%    184.750000   50.000000   55.000000   50.000000   49.750000   50.000000   
    50%    364.500000   65.000000   75.000000   70.000000   65.000000   70.000000   
    75%    539.250000   80.000000  100.000000   90.000000   95.000000   90.000000   
    max    721.000000  255.000000  190.000000  230.000000  194.000000  230.000000   
    
                Speed  Generation  
    count  800.000000   800.00000  
    mean    68.277500     3.32375  
    std     29.060474     1.66129  
    min      5.000000     1.00000  
    25%     45.000000     2.00000  
    50%     65.000000     3.00000  
    75%     90.000000     5.00000  
    max    180.000000     6.00000  
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>520</th>
      <td>469</td>
      <td>Yanmega</td>
      <td>Bug</td>
      <td>Flying</td>
      <td>86</td>
      <td>76</td>
      <td>86</td>
      <td>116</td>
      <td>56</td>
      <td>95</td>
      <td>4</td>
      <td>False</td>
    </tr>
    <tr>
      <th>698</th>
      <td>637</td>
      <td>Volcarona</td>
      <td>Bug</td>
      <td>Fire</td>
      <td>85</td>
      <td>60</td>
      <td>65</td>
      <td>135</td>
      <td>105</td>
      <td>100</td>
      <td>5</td>
      <td>False</td>
    </tr>
    <tr>
      <th>231</th>
      <td>214</td>
      <td>Heracross</td>
      <td>Bug</td>
      <td>Fighting</td>
      <td>80</td>
      <td>125</td>
      <td>75</td>
      <td>40</td>
      <td>95</td>
      <td>85</td>
      <td>2</td>
      <td>False</td>
    </tr>
    <tr>
      <th>232</th>
      <td>214</td>
      <td>HeracrossMega Heracross</td>
      <td>Bug</td>
      <td>Fighting</td>
      <td>80</td>
      <td>185</td>
      <td>115</td>
      <td>40</td>
      <td>105</td>
      <td>75</td>
      <td>2</td>
      <td>False</td>
    </tr>
    <tr>
      <th>678</th>
      <td>617</td>
      <td>Accelgor</td>
      <td>Bug</td>
      <td>NaN</td>
      <td>80</td>
      <td>70</td>
      <td>40</td>
      <td>100</td>
      <td>60</td>
      <td>145</td>
      <td>5</td>
      <td>False</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>106</th>
      <td>98</td>
      <td>Krabby</td>
      <td>Water</td>
      <td>NaN</td>
      <td>30</td>
      <td>105</td>
      <td>90</td>
      <td>25</td>
      <td>25</td>
      <td>50</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>125</th>
      <td>116</td>
      <td>Horsea</td>
      <td>Water</td>
      <td>NaN</td>
      <td>30</td>
      <td>40</td>
      <td>70</td>
      <td>70</td>
      <td>25</td>
      <td>60</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>129</th>
      <td>120</td>
      <td>Staryu</td>
      <td>Water</td>
      <td>NaN</td>
      <td>30</td>
      <td>45</td>
      <td>55</td>
      <td>70</td>
      <td>55</td>
      <td>85</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>139</th>
      <td>129</td>
      <td>Magikarp</td>
      <td>Water</td>
      <td>NaN</td>
      <td>20</td>
      <td>10</td>
      <td>55</td>
      <td>15</td>
      <td>20</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
    </tr>
    <tr>
      <th>381</th>
      <td>349</td>
      <td>Feebas</td>
      <td>Water</td>
      <td>NaN</td>
      <td>20</td>
      <td>15</td>
      <td>20</td>
      <td>10</td>
      <td>55</td>
      <td>80</td>
      <td>3</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>800 rows × 12 columns</p>
</div>



### Making changes to the data


```python
# Add a new column Total
df['Total'] = df['HP'] + df['Attack'] + df['Defense'] + df ['Sp. Atk'] + df['Sp. Def'] + df['Speed']
# Get rid of the column
df = df.drop(columns=['Total'])
# Another method   iloc=integerlocation   axis=1 adds horizontally
df['Total'] = df.iloc[:, 4:10].sum(axis=1)

df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Bulbasaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>45</td>
      <td>49</td>
      <td>49</td>
      <td>65</td>
      <td>65</td>
      <td>45</td>
      <td>1</td>
      <td>False</td>
      <td>318</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Ivysaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>60</td>
      <td>62</td>
      <td>63</td>
      <td>80</td>
      <td>80</td>
      <td>60</td>
      <td>1</td>
      <td>False</td>
      <td>405</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>82</td>
      <td>83</td>
      <td>100</td>
      <td>100</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>525</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>VenusaurMega Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>100</td>
      <td>123</td>
      <td>122</td>
      <td>120</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>625</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Charmander</td>
      <td>Fire</td>
      <td>NaN</td>
      <td>39</td>
      <td>52</td>
      <td>43</td>
      <td>60</td>
      <td>50</td>
      <td>65</td>
      <td>1</td>
      <td>False</td>
      <td>309</td>
    </tr>
  </tbody>
</table>
</div>



### Saving the data


```python
df.to_csv('modified.csv', index=False)
# index=False gets rid of the index column

df.to_csv('modified.txt', index=False, sep='\t')
```

### Filtering Data


```python
# new dataframe = Grass Poison types with <70 HP
new_df = df.loc[(df['Type 1'] == 'Grass') & (df['Type 2'] == 'Poison') & (df['HP'] > 70)]
# Reset index and drop old one
#                   inplace makes it so we don't have to do new_df = 
new_df.reset_index(drop=True, inplace=True)
new_df

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>3</td>
      <td>Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>82</td>
      <td>83</td>
      <td>100</td>
      <td>100</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>525</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3</td>
      <td>VenusaurMega Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>100</td>
      <td>123</td>
      <td>122</td>
      <td>120</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>625</td>
    </tr>
    <tr>
      <th>2</th>
      <td>45</td>
      <td>Vileplume</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>75</td>
      <td>80</td>
      <td>85</td>
      <td>110</td>
      <td>90</td>
      <td>50</td>
      <td>1</td>
      <td>False</td>
      <td>490</td>
    </tr>
    <tr>
      <th>3</th>
      <td>71</td>
      <td>Victreebel</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>105</td>
      <td>65</td>
      <td>100</td>
      <td>70</td>
      <td>70</td>
      <td>1</td>
      <td>False</td>
      <td>490</td>
    </tr>
    <tr>
      <th>4</th>
      <td>591</td>
      <td>Amoonguss</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>114</td>
      <td>85</td>
      <td>70</td>
      <td>85</td>
      <td>80</td>
      <td>30</td>
      <td>5</td>
      <td>False</td>
      <td>464</td>
    </tr>
  </tbody>
</table>
</div>



##### Filter if a column contains a specific string


```python
# Get all the Megas 
df.loc[df['Name'].str.contains('Mega')]

# Get all pokemon WITHOUT 'Mega'   (put ~)
df.loc[~df['Name'].str.contains('Mega')]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Bulbasaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>45</td>
      <td>49</td>
      <td>49</td>
      <td>65</td>
      <td>65</td>
      <td>45</td>
      <td>1</td>
      <td>False</td>
      <td>318</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Ivysaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>60</td>
      <td>62</td>
      <td>63</td>
      <td>80</td>
      <td>80</td>
      <td>60</td>
      <td>1</td>
      <td>False</td>
      <td>405</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Venusaur</td>
      <td>Grass</td>
      <td>Poison</td>
      <td>80</td>
      <td>82</td>
      <td>83</td>
      <td>100</td>
      <td>100</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>525</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Charmander</td>
      <td>Fire</td>
      <td>NaN</td>
      <td>39</td>
      <td>52</td>
      <td>43</td>
      <td>60</td>
      <td>50</td>
      <td>65</td>
      <td>1</td>
      <td>False</td>
      <td>309</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Charmeleon</td>
      <td>Fire</td>
      <td>NaN</td>
      <td>58</td>
      <td>64</td>
      <td>58</td>
      <td>80</td>
      <td>65</td>
      <td>80</td>
      <td>1</td>
      <td>False</td>
      <td>405</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>794</th>
      <td>718</td>
      <td>Zygarde50% Forme</td>
      <td>Dragon</td>
      <td>Ground</td>
      <td>108</td>
      <td>100</td>
      <td>121</td>
      <td>81</td>
      <td>95</td>
      <td>95</td>
      <td>6</td>
      <td>True</td>
      <td>600</td>
    </tr>
    <tr>
      <th>795</th>
      <td>719</td>
      <td>Diancie</td>
      <td>Rock</td>
      <td>Fairy</td>
      <td>50</td>
      <td>100</td>
      <td>150</td>
      <td>100</td>
      <td>150</td>
      <td>50</td>
      <td>6</td>
      <td>True</td>
      <td>600</td>
    </tr>
    <tr>
      <th>797</th>
      <td>720</td>
      <td>HoopaHoopa Confined</td>
      <td>Psychic</td>
      <td>Ghost</td>
      <td>80</td>
      <td>110</td>
      <td>60</td>
      <td>150</td>
      <td>130</td>
      <td>70</td>
      <td>6</td>
      <td>True</td>
      <td>600</td>
    </tr>
    <tr>
      <th>798</th>
      <td>720</td>
      <td>HoopaHoopa Unbound</td>
      <td>Psychic</td>
      <td>Dark</td>
      <td>80</td>
      <td>160</td>
      <td>60</td>
      <td>170</td>
      <td>130</td>
      <td>80</td>
      <td>6</td>
      <td>True</td>
      <td>680</td>
    </tr>
    <tr>
      <th>799</th>
      <td>721</td>
      <td>Volcanion</td>
      <td>Fire</td>
      <td>Water</td>
      <td>80</td>
      <td>110</td>
      <td>120</td>
      <td>130</td>
      <td>90</td>
      <td>70</td>
      <td>6</td>
      <td>True</td>
      <td>600</td>
    </tr>
  </tbody>
</table>
<p>751 rows × 13 columns</p>
</div>



##### Filtering with regular expressions


```python
import re

# Get all pokemon of Fire or Grass type
df.loc[df['Type 1'].str.contains('Fire|Grass', regex=True)]

df.loc[df['Name'].str.contains('^pi[a-z]*', flags=re.I, regex=True)]

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>20</th>
      <td>16</td>
      <td>Pidgey</td>
      <td>Normal</td>
      <td>Flying</td>
      <td>40</td>
      <td>45</td>
      <td>40</td>
      <td>35</td>
      <td>35</td>
      <td>56</td>
      <td>1</td>
      <td>False</td>
      <td>251</td>
    </tr>
    <tr>
      <th>21</th>
      <td>17</td>
      <td>Pidgeotto</td>
      <td>Normal</td>
      <td>Flying</td>
      <td>63</td>
      <td>60</td>
      <td>55</td>
      <td>50</td>
      <td>50</td>
      <td>71</td>
      <td>1</td>
      <td>False</td>
      <td>349</td>
    </tr>
    <tr>
      <th>22</th>
      <td>18</td>
      <td>Pidgeot</td>
      <td>Normal</td>
      <td>Flying</td>
      <td>83</td>
      <td>80</td>
      <td>75</td>
      <td>70</td>
      <td>70</td>
      <td>101</td>
      <td>1</td>
      <td>False</td>
      <td>479</td>
    </tr>
    <tr>
      <th>23</th>
      <td>18</td>
      <td>PidgeotMega Pidgeot</td>
      <td>Normal</td>
      <td>Flying</td>
      <td>83</td>
      <td>80</td>
      <td>80</td>
      <td>135</td>
      <td>80</td>
      <td>121</td>
      <td>1</td>
      <td>False</td>
      <td>579</td>
    </tr>
    <tr>
      <th>30</th>
      <td>25</td>
      <td>Pikachu</td>
      <td>Electric</td>
      <td>NaN</td>
      <td>35</td>
      <td>55</td>
      <td>40</td>
      <td>50</td>
      <td>50</td>
      <td>90</td>
      <td>1</td>
      <td>False</td>
      <td>320</td>
    </tr>
    <tr>
      <th>136</th>
      <td>127</td>
      <td>Pinsir</td>
      <td>Bug</td>
      <td>NaN</td>
      <td>65</td>
      <td>125</td>
      <td>100</td>
      <td>55</td>
      <td>70</td>
      <td>85</td>
      <td>1</td>
      <td>False</td>
      <td>500</td>
    </tr>
    <tr>
      <th>137</th>
      <td>127</td>
      <td>PinsirMega Pinsir</td>
      <td>Bug</td>
      <td>Flying</td>
      <td>65</td>
      <td>155</td>
      <td>120</td>
      <td>65</td>
      <td>90</td>
      <td>105</td>
      <td>1</td>
      <td>False</td>
      <td>600</td>
    </tr>
    <tr>
      <th>186</th>
      <td>172</td>
      <td>Pichu</td>
      <td>Electric</td>
      <td>NaN</td>
      <td>20</td>
      <td>40</td>
      <td>15</td>
      <td>35</td>
      <td>35</td>
      <td>60</td>
      <td>2</td>
      <td>False</td>
      <td>205</td>
    </tr>
    <tr>
      <th>219</th>
      <td>204</td>
      <td>Pineco</td>
      <td>Bug</td>
      <td>NaN</td>
      <td>50</td>
      <td>65</td>
      <td>90</td>
      <td>35</td>
      <td>35</td>
      <td>15</td>
      <td>2</td>
      <td>False</td>
      <td>290</td>
    </tr>
    <tr>
      <th>239</th>
      <td>221</td>
      <td>Piloswine</td>
      <td>Ice</td>
      <td>Ground</td>
      <td>100</td>
      <td>100</td>
      <td>80</td>
      <td>60</td>
      <td>60</td>
      <td>50</td>
      <td>2</td>
      <td>False</td>
      <td>450</td>
    </tr>
    <tr>
      <th>438</th>
      <td>393</td>
      <td>Piplup</td>
      <td>Water</td>
      <td>NaN</td>
      <td>53</td>
      <td>51</td>
      <td>53</td>
      <td>61</td>
      <td>56</td>
      <td>40</td>
      <td>4</td>
      <td>False</td>
      <td>314</td>
    </tr>
    <tr>
      <th>558</th>
      <td>499</td>
      <td>Pignite</td>
      <td>Fire</td>
      <td>Fighting</td>
      <td>90</td>
      <td>93</td>
      <td>55</td>
      <td>70</td>
      <td>55</td>
      <td>55</td>
      <td>5</td>
      <td>False</td>
      <td>418</td>
    </tr>
    <tr>
      <th>578</th>
      <td>519</td>
      <td>Pidove</td>
      <td>Normal</td>
      <td>Flying</td>
      <td>50</td>
      <td>55</td>
      <td>50</td>
      <td>36</td>
      <td>30</td>
      <td>43</td>
      <td>5</td>
      <td>False</td>
      <td>264</td>
    </tr>
  </tbody>
</table>
</div>



### Conditional changes


```python
# Change all 'Fire' types to 'Flamer'
df.loc[df['Type 1'] == 'Fire', 'Type 1'] = 'Flamer'
print(df)
```

           #                   Name   Type 1  Type 2  HP  Attack  Defense  \
    0      1              Bulbasaur    Grass  Poison  45      49       49   
    1      2                Ivysaur    Grass  Poison  60      62       63   
    2      3               Venusaur    Grass  Poison  80      82       83   
    3      3  VenusaurMega Venusaur    Grass  Poison  80     100      123   
    4      4             Charmander   Flamer     NaN  39      52       43   
    ..   ...                    ...      ...     ...  ..     ...      ...   
    795  719                Diancie     Rock   Fairy  50     100      150   
    796  719    DiancieMega Diancie     Rock   Fairy  50     160      110   
    797  720    HoopaHoopa Confined  Psychic   Ghost  80     110       60   
    798  720     HoopaHoopa Unbound  Psychic    Dark  80     160       60   
    799  721              Volcanion   Flamer   Water  80     110      120   
    
         Sp. Atk  Sp. Def  Speed  Generation  Legendary  Total  
    0         65       65     45           1      False    318  
    1         80       80     60           1      False    405  
    2        100      100     80           1      False    525  
    3        122      120     80           1      False    625  
    4         60       50     65           1      False    309  
    ..       ...      ...    ...         ...        ...    ...  
    795      100      150     50           6       True    600  
    796      160      110    110           6       True    700  
    797      150      130     70           6       True    600  
    798      170      130     80           6       True    680  
    799      130       90     70           6       True    600  
    
    [800 rows x 13 columns]
    

### Aggregate statistics (Groupby)


```python
# Restore dataframe with our checkpoint
df = pd.read_csv('modified.csv')

df['count'] = 1

df.groupby(['Type 1', 'Type 2']).count()['count']
```




    Type 1  Type 2  
    Bug     Electric     2
            Fighting     2
            Fire         2
            Flying      14
            Ghost        1
                        ..
    Water   Ice          3
            Poison       3
            Psychic      5
            Rock         4
            Steel        1
    Name: count, Length: 136, dtype: int64



### Working with large amounts of data


```python
# When working with a large database, chunksize allows us to take 5 rows at a time
for index, df in enumerate(pd.read_csv('modified.csv', chunksize=5)):
    print(f"CHUNK {index + 1}")
    print(df)

    # Stop early for demonstration purposes
    if index == 5:
        break
```

    CHUNK 1
       #                   Name Type 1  Type 2  HP  Attack  Defense  Sp. Atk  \
    0  1              Bulbasaur  Grass  Poison  45      49       49       65   
    1  2                Ivysaur  Grass  Poison  60      62       63       80   
    2  3               Venusaur  Grass  Poison  80      82       83      100   
    3  3  VenusaurMega Venusaur  Grass  Poison  80     100      123      122   
    4  4             Charmander   Fire     NaN  39      52       43       60   
    
       Sp. Def  Speed  Generation  Legendary  Total  
    0       65     45           1      False    318  
    1       80     60           1      False    405  
    2      100     80           1      False    525  
    3      120     80           1      False    625  
    4       50     65           1      False    309  
    CHUNK 2
       #                       Name Type 1  Type 2  HP  Attack  Defense  Sp. Atk  \
    5  5                 Charmeleon   Fire     NaN  58      64       58       80   
    6  6                  Charizard   Fire  Flying  78      84       78      109   
    7  6  CharizardMega Charizard X   Fire  Dragon  78     130      111      130   
    8  6  CharizardMega Charizard Y   Fire  Flying  78     104       78      159   
    9  7                   Squirtle  Water     NaN  44      48       65       50   
    
       Sp. Def  Speed  Generation  Legendary  Total  
    5       65     80           1      False    405  
    6       85    100           1      False    534  
    7       85    100           1      False    634  
    8      115    100           1      False    634  
    9       64     43           1      False    314  
    CHUNK 3
         #                     Name Type 1  Type 2  HP  Attack  Defense  Sp. Atk  \
    10   8                Wartortle  Water     NaN  59      63       80       65   
    11   9                Blastoise  Water     NaN  79      83      100       85   
    12   9  BlastoiseMega Blastoise  Water     NaN  79     103      120      135   
    13  10                 Caterpie    Bug     NaN  45      30       35       20   
    14  11                  Metapod    Bug     NaN  50      20       55       25   
    
        Sp. Def  Speed  Generation  Legendary  Total  
    10       80     58           1      False    405  
    11      105     78           1      False    530  
    12      115     78           1      False    630  
    13       20     45           1      False    195  
    14       25     30           1      False    205  
    CHUNK 4
         #                   Name Type 1  Type 2  HP  Attack  Defense  Sp. Atk  \
    15  12             Butterfree    Bug  Flying  60      45       50       90   
    16  13                 Weedle    Bug  Poison  40      35       30       20   
    17  14                 Kakuna    Bug  Poison  45      25       50       25   
    18  15               Beedrill    Bug  Poison  65      90       40       45   
    19  15  BeedrillMega Beedrill    Bug  Poison  65     150       40       15   
    
        Sp. Def  Speed  Generation  Legendary  Total  
    15       80     70           1      False    395  
    16       20     50           1      False    195  
    17       25     35           1      False    205  
    18       80     75           1      False    395  
    19       80    145           1      False    495  
    CHUNK 5
         #                 Name  Type 1  Type 2  HP  Attack  Defense  Sp. Atk  \
    20  16               Pidgey  Normal  Flying  40      45       40       35   
    21  17            Pidgeotto  Normal  Flying  63      60       55       50   
    22  18              Pidgeot  Normal  Flying  83      80       75       70   
    23  18  PidgeotMega Pidgeot  Normal  Flying  83      80       80      135   
    24  19              Rattata  Normal     NaN  30      56       35       25   
    
        Sp. Def  Speed  Generation  Legendary  Total  
    20       35     56           1      False    251  
    21       50     71           1      False    349  
    22       70    101           1      False    479  
    23       80    121           1      False    579  
    24       35     72           1      False    253  
    CHUNK 6
         #      Name  Type 1  Type 2  HP  Attack  Defense  Sp. Atk  Sp. Def  \
    25  20  Raticate  Normal     NaN  55      81       60       50       70   
    26  21   Spearow  Normal  Flying  40      60       30       31       31   
    27  22    Fearow  Normal  Flying  65      90       65       61       61   
    28  23     Ekans  Poison     NaN  35      60       44       40       54   
    29  24     Arbok  Poison     NaN  60      85       69       65       79   
    
        Speed  Generation  Legendary  Total  
    25     97           1      False    413  
    26     70           1      False    262  
    27    100           1      False    442  
    28     55           1      False    288  
    29     80           1      False    438  
    

##### Getting the count one chunk at a time


```python
# Create empty df with same column names
new_df = pd.DataFrame(columns=df.columns)

for df in pd.read_csv('modified.csv', chunksize = 5):
    results = df.groupby(['Type 1']).count()
    
    new_df = pd.concat([new_df, results])

new_df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>#</th>
      <th>Name</th>
      <th>Type 1</th>
      <th>Type 2</th>
      <th>HP</th>
      <th>Attack</th>
      <th>Defense</th>
      <th>Sp. Atk</th>
      <th>Sp. Def</th>
      <th>Speed</th>
      <th>Generation</th>
      <th>Legendary</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Fire</th>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Grass</th>
      <td>4</td>
      <td>4</td>
      <td>NaN</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Fire</th>
      <td>4</td>
      <td>4</td>
      <td>NaN</td>
      <td>3</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>4</td>
    </tr>
    <tr>
      <th>Water</th>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Bug</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Fairy</th>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Flying</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Fire</th>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>Psychic</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
    <tr>
      <th>Rock</th>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>433 rows × 13 columns</p>
</div>


