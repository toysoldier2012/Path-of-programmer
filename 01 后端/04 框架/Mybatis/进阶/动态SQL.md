
# `where` `if`

- `test`

``` xml
<!--    List<City> getCitiesByCondition(City city);-->  
<select id="getCitiesByCondition" resultMap="CityDynamicSearch">  
    select * from city  
    <where>  
        <if test="id != null and id != 0">  
            and city_id > #{id}  
        </if>  
        <if test="name != null and name != ''">  
            and city like "%"#{name}"%"  
        </if>  
        <if test="lastUpdate != null">  
            and last_update > #{lastUpdate}  
        </if>  
    </where>
</select>
```

# `trim`

- `prefix`
- `prifixOverrides`
- `suffix`
- `suffixOverrides`

``` xml
<trim prefix="where" prefixOverrides="" suffix="" suffixOverrides="and">
	<if test="id != null and id != 0">  
		city_id > #{id} and
	</if>  
	<if test="name != null and name != ''">  
		city like "%"#{name}"%" and
	</if>  
	<if test="lastUpdate != null">  
		last_update > #{lastUpdate}
	</if> 
</trim>
```

# `choose when otherwise`

类似于`switch`结构，但是判断条件可以随意写

``` xml
<select id="getCitiesByCondition" resultMap="CityDynamicSearch">  
	select * from city  
	<where>  
		<choose>                
			<when test="id != null and id != 0">  
				city_id > #{id}  
			</when>  
			<when test="name != null and name != ''">  
				city like "%"#{name}"%"  
			</when>  
			<otherwise>
                last_update > #{lastUpdate}  
			</otherwise>  
		</choose>
	</where>
</select>
```

# `foreach`

- `collection`
- `item`
- `separator`
- `open`
- `close`

``` xml
<!--    void insertCities(@Param("cities") List<City> listCities);-->  
<insert id="insertCities">  
	insert into city (city_id, city, country_id, last_update)  
	values  
	<foreach collection="cities" item="city" separator=",">  
		(null, #{city.name}, #{city.country.countryId}, #{city.lastUpdate})  
	</foreach>  
</insert>
```

``` xml
<!--    void deleteCities(@Param("citiesId") Integer[] citiesId);-->  
<delete id="deleteCities">  
	delete from city where city_id in  
	<foreach collection="citiesId" item="cityId" open="(" close=")" separator=",">  
		#{cityId}  
	</foreach>  
</delete>
```

``` xml
delete from city  
<foreach collection="citiesId" item="cityId" open="where" separator="or">  
    city_id = #{cityId}  
</foreach>
```

# `sql`和`include`

``` xml
<sql id="countryColomns">  
    country_id, country, last_update  
</sql>

<include refid="countryColomns"/>
```