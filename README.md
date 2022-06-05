# Iran-province-and-cities
List of provinces and their cities in Iran formatted in JSON

React Example: (json file imported as `iranCities`)
```
function MyComponent() {
  const [cities, setCities] = useState([]);
  
  return (
    <>
      <select
        name="province"
        onBlur={(e) => {
          e.preventDefault();
          setCities(
            iranCities.find((v) => v.province === e.target.value)
              ?.cities
          );
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
