### [x] create-react app
	- npx create-react-app sample
	- npx create-react-app sample_type --template typescript
	- yarn create react-app sample_type --template typescript
### [ ] state management
	- function component (stateless) 
    	- can use useState() [value, setValue] as [currentStateValue, setStateValue]
    	- Ref: https://react.dev/reference/react/useState
    	- Ex: ```js
			function CounterApp(props: CounterAppType) => {

			const [value, setValue] = useState(props.initialValue ?? 0);

			var increase = () => {
				setValue(value + 1);
				Logger.d(this);
			}

			var decrease = () => {
				setValue(value - 1);
				Logger.d(this);
			}

			// Similar to componentDidMount and componentDidUpdate:
			useEffect(() => {
				// Update the document title using the browser API
				document.title = `You clicked ${value} times`;
			});

		return (
					<div>
					Value is {value}
					<button onClick={decrease}>decrease</button>
					<button onClick={increase}>increase</button>
				</div>
				)

		}
		```
	- class component (stateful)
    	- can use state and setState
    	- Ref: https://react.dev/reference/react/Component#setstate
      	- Ex: ```js
			class CounterApp extends React.Component<CounterAppType> {

				state = {
					value: this.props.initialValue ?? 0,
				};

				componentDidMount(): void {
					document.title = `You clicked ${this.state.value} times`;
				}

				componentDidUpdate(prevProps: Readonly<CounterAppType>, prevState: Readonly<{}>, snapshot?: any): void {
					document.title = `You clicked ${this.state.value} times`;
				}

				increase = () => {
					this.setState({ value: this.state.value + 1 })
					Logger.d(this);
				}
				decrease = () => {
					this.setState({ value: this.state.value - 1 })
					Logger.d(this);
				}

				render(): React.ReactNode {
					return (
						<div>
							Value is {this.state.value}
							<button onClick={this.decrease}>decrease</button>
							<button onClick={this.increase}>increase</button>
						</div>
					);
				}

			}
			```
	- createContext and useContext
    	- avoid nested props from parent to child/childen
    	- Ref: https://react.dev/reference/react/useContext
    	- Eg: ```js

    		```
### [ ] using route
	- pre-defind route by path and name
	- react-router-dom (for web)
	- react-route-native (for native)
	- v5 compare: https://v5.reactrouter.com/native/guides/quick-start
	- v6 https://reactrouter.com/en/main/router-components/native-router
	- pre-defind name route: https://reactrouter.com/en/main/start/overview

### [ ] using fetch and axios

### [ ] dom api
	- dialog
	- console
	- 

### [x] architecture app
	- The "assets" folder holds static files like logos, fonts, and images.
	- The "components" folder contains UI codes, like buttons and forms.
    	+ inside input_component directory
      	- "Input.js"- This file usually contains all the functionalities and logic that are to be required for the custom input component.
      	- "Input.css"- This file contains rules related explicitly to styling input components
      	- "Input.test.js"- This file contains the test cases that ensure all components behave as expected.
	- The "views" folder has web images.
	- The "service" folder contains code for communicating with external APIs.
	- The "utils" folder simplifies reusable snippet functions.
	- The " hooks" folder contains reusable code and new component logic.
	- The "store" folder holds state management like Redux.
	- The "App.js" folder serves as the primary component of the application.
	- "Index.js" The React app entry point starts here.
	- "Index.css" is the application’s global sheet style for styled-components.

[ ] testing both javascript and typescript

[ ] pre-defind ui react framework
	- for admin panel: https://github.com/marmelab/react-admin
	- for native to web support: https://github.com/necolas/react-native-web
	- ui/ux framework: https://ant.design/docs/react/introduce