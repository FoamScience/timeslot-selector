# timeslot-selector

Hours picker by week day with custom hours range

## Usage

- set `data-name` attr for getting value with form submiting

### UMD Module
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
</head>
<body>
    <div id="input" data-name="form-name"></div>

    <script src="https://unpkg.com/week-hours-picker@latest/src/index.js"></script>
    <script>
        (() => {    
            // initialState { [row]: [hours] }
            const state = {
                0: [1, 2, 5, 10],
                5: [4, 9, 10, 20],
            }
            
            // change callback
            function handleStateChange(newState) {
                console.log(newState)
            }

            const options = {

                // custom days names (it's default values)
                days: {
                    0: 'Monday',
                    1: 'Tuesday',
                    2: 'Wednesday',
                    3: 'Thursday',
                    4: 'Friday',
                    5: 'Saturday',
                    6: 'Sunday',
                },
                
                // custom class names for dom elements (it's default values)
                classes: {
                    active: '',
                    aside: '',
                    body: '',
                    container: '',
                    day: '',
                    grid: '',
                    header: '',
                    headerHour: '',
                    hour: '',
                    input: '',
                    node: '',
                    row: '',
                },

                // custom start (included) and end hours (excluded)
                startHour: 7,
                endHour: 18
            }

            weekHoursPicker(
                document.querySelector('#input'), // required
                state, // optional
                handleStateChange, // optional
                options, // optional
            )
        })()
    </script>
</body>
</html>
```

### ESM Module

```javascript
import weekHoursPicker from 'week-hours-picker'

weekHoursPicker(
    document.querySelector('#input'), // required
    state, // optional
    handleStateChange, // optional
    options, // optional
)
```
