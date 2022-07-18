# Iran-province-and-cities
List of provinces and their cities in Iran formatted in JSON

## React Example
json file is imported as `iranCities`

```jsx
import iranCities from './path-to-json-file.json';

function MyComponent() {
  const [province, setProvince] = useState('');
  const [cities, setCities] = useState([]);

  useEffect(() => {
    if (province) {
      const foundProvince = iranCities.find((v) => v.province === province);
      
      if (foundProvince) {
        setCities(foundProvince.cities);
      }
      
    } else {
      setCities([]);
    }
    
  }, [province]);
  
  return (
    <>
      <select
        name="province"
        onChange={(e) => {
          setProvince(e.target.value);
        }}
      >
        <opton value="">انتخاب استان</option>
        {iranCities.map((province, k) => (
          <option
            value={province.province}
            key={`province_${k}`}
          >
            {province.province}
          </option>
        ))}
      </select>

      <select name="city">
        <option value="">انتخاب شهر</option>

        {cities.map((city, k) => (
          <option key={`city_${k}`} value={city.name}>
            {city.name}
          </option>
        ))}
      </select>
    </>
  );
}
```
