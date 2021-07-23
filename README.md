# Hi, I'm Kevin and this is my portfolio 🇺🇸<br/>Olá, Eu sou o Kevin e esse é meu portfólio 🇧🇷
<details>
    
<summary>See the english [EN] portfolio</summary>

## Complete IOS App Development Bootcamp Projects
<details>
    
<summary>See more about Complete IOS App Development Bootcamp</summary>

### Advanced Swift Classroom 1
<details>
    
<summary>See more about Advanced Swift Classroom 1</summary>
    
#### Understanding Getters and Setters
```swift
let one: Int = 1

var two: Int {
    get {
        return one + 1
    }
}
 ```
 
```swift
let one: Int = 1

var two: Int {
    set {
        if two != 2 {
            print("two != 2 !!!")
        }
    }
}
 ```
#### Understanding Observed properties
```swift
var one: Int = 1 {
    willSet {
        print("The variable is about to chage")
    }
    didSet {
        print("The variable changed")
    }
}
 ```
    
</details>

### Flash Chat App
![morflax_things-6](https://user-images.githubusercontent.com/49958388/126725712-efa574b9-29ba-44d9-8913-068a135f125c.png)
<details>
    
<summary>See more about Flash Chat App</summary>
    
#### Using Cocoapods to get 3rd party libraries
Podfile
```markdown
platform :ios, '13.0'

target 'Flash Chat iOS13' do

  use_frameworks!

  pod 'CLTypingLabel', '~> 0.4.0'
  pod 'Firebase/Auth'
  pod 'Firebase/Firestore'

end
 ```
 
AppDelegate.swift
```swift
import IQKeyboardManagerSwift

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.
        FirebaseApp.configure()
        Firestore.firestore()
        
        IQKeyboardManager.shared.enable = true
        IQKeyboardManager.shared.enableAutoToolbar = false
        IQKeyboardManager.shared.shouldResignOnTouchOutside = true
        
        return true
    }
//[...]
}
 ```

WelcomeViewController.swift
```swift
@IBOutlet weak var titleLabel: CLTypingLabel!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        titleLabel.text = K.appName
    }
 ```

#### Using Firebase Auth to sign in existing users
LoginViewController.swift
```swift
    @IBAction func loginPressed(_ sender: UIButton) {
        
        if let email = emailTextfield.text, let password = passwordTextfield.text {
            Auth.auth().signIn(withEmail: email, password: password) { [weak self] authResult, error in
                if let e = error {
                    print(e.localizedDescription)
                } else {
                    self!.performSegue(withIdentifier: K.loginSegue, sender: self)
                }
            }
        }
    }
 ```

#### Using Firebase to send chat messages to database
ChatViewController.swift
```swift
    @IBAction func sendPressed(_ sender: UIButton) {
        if let messageBody = messageTextfield.text, let messageSender = Auth.auth().currentUser?.email {
            db.collection(K.FStore.collectionName).addDocument(data: [
                                                                K.FStore.senderField: messageSender,
                                                                K.FStore.bodyField: messageBody,
                                                                K.FStore.dateField: Date().timeIntervalSince1970
            ]) { error in
                if let e = error {
                    print(e)
                } else {
                    print("sendPressed okay")
                    DispatchQueue.main.async {
                        self.messageTextfield.text = ""
                    }
                }
            }
        }
    }
```

#### Using Xib to create a custom TableViewCell
MessageCell.swift
```swift
class MessageCell: UITableViewCell {

    @IBOutlet weak var messageBubble: UIView!
    @IBOutlet weak var label: UILabel!
    @IBOutlet weak var rightImageView: UIImageView!
    @IBOutlet weak var leftImageView: UIImageView!
    
    override func awakeFromNib() {
        super.awakeFromNib()
        
        messageBubble.layer.cornerRadius = messageBubble.frame.size.height / 4
    }

    override func setSelected(_ selected: Bool, animated: Bool) {
        super.setSelected(selected, animated: animated)

        
    }
    
}
```
ChatViewController.swift
```swift
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        
    let cell = tableView.dequeueReusableCell(withIdentifier: K.cellIdentifier, for: indexPath) as! MessageCell
 //[...]
 }
```
MessageCell.xib

<img width="533" alt="Captura de Tela 2021-07-22 às 19 50 18" src="https://user-images.githubusercontent.com/49958388/126718746-106cc259-de67-42f7-bff3-89b99b952d56.png">

#### Understanding Upcast and Downcast
```swift
    
    let subclassObject = Subclass()
    let classObject = Class()

    if let object = classObject is Subclass {
      let object = classObject as! Subclass
    }
    
    let object = classObject as? Subclass
    
    let object = subclassObject as Class
    
```

#### Understanding ViewController Lifecycle
![image](https://user-images.githubusercontent.com/49958388/126719944-54812cfe-e5b5-4dd5-8927-5f8241778423.png)

#### Understanding App Lifecycle
![image](https://user-images.githubusercontent.com/49958388/126720044-e7b4d813-2d71-46cc-9bec-245e0268f65d.png)
AppDelegate.swift
```swift
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {}

    func application(_ application: UIApplication, configurationForConnecting connectingSceneSession: UISceneSession, options: UIScene.ConnectionOptions) -> UISceneConfiguration {}

    func application(_ application: UIApplication, didDiscardSceneSessions sceneSessions: Set<UISceneSession>) {}
```

SceneDelegate.swift
```swift
    func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {}

    func sceneDidDisconnect(_ scene: UIScene) {}

    func sceneDidBecomeActive(_ scene: UIScene) {}

    func sceneWillResignActive(_ scene: UIScene) {}

    func sceneWillEnterForeground(_ scene: UIScene) {}

    func sceneDidEnterBackground(_ scene: UIScene) {}
```

</details>
    
### Clima App
![morflax_things-5](https://user-images.githubusercontent.com/49958388/126725670-302882be-e602-44a5-a18c-2d198312c165.png)
<details>
    
<summary>See more about Clima App</summary>
    
#### Using Computed Properties
WeatherViewController.swift
```swift
class WeatherViewController: UIViewController {

    @IBOutlet weak var conditionImageView: UIImageView!
    @IBOutlet weak var temperatureLabel: UILabel!
    @IBOutlet weak var cityLabel: UILabel!
    @IBOutlet weak var searchTextField: UITextField!
    
    var weatherManager = WeatherManager()
    let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        locationManager.delegate = self
        weatherManager.delegate = self
        searchTextField.delegate = self
        
        locationManager.requestWhenInUseAuthorization()
        locationManager.requestLocation()
    }
//[...]
}

extension WeatherViewController: CLLocationManagerDelegate {
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        if let location = locations.last {
            locationManager.stopUpdatingLocation()
            let lat = location.coordinate.latitude
            let lon = location.coordinate.longitude
            weatherManager.fetchWeather(latitude: lat, longitude: lon)
        }
    }
    
    func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
        print(error)
    }
}
 ```
 
#### Using CoreLocation to get location data
WeatherViewController.swift
```swift
    let locationManager = CLLocationManager()
    
        override func viewDidLoad() {
            super.viewDidLoad()
            locationManager.delegate = self
            weatherManager.delegate = self
            searchTextField.delegate = self
        
            locationManager.requestWhenInUseAuthorization()
            locationManager.requestLocation()
        }
    
extension WeatherViewController: CLLocationManagerDelegate {
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        if let location = locations.last {
            locationManager.stopUpdatingLocation()
            let lat = location.coordinate.latitude
            let lon = location.coordinate.longitude
            weatherManager.fetchWeather(latitude: lat, longitude: lon)
        }
    }
    
    func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
        print(error)
    }
}

 ```
 
#### Understanding the Delegate Design pattern and using it to pass data between a model class and ViewController

![image](https://user-images.githubusercontent.com/49958388/126714234-d36d20c2-6852-40a8-94c6-093fd03fccfa.png)
    
WeatherViewController.swift
```swift
class WeatherViewController: UIViewController {
//[...]
    var weatherManager = WeatherManager()
    let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        locationManager.delegate = self
        weatherManager.delegate = self
        searchTextField.delegate = self
        
        locationManager.requestWhenInUseAuthorization()
        locationManager.requestLocation()
    }
}

extension WeatherViewController: WeatherManagerDelegate {
    func didUpdateWeather(_ weatherManager: WeatherManager, weather: WeatherModel) {
        DispatchQueue.main.async {
            self.temperatureLabel.text = weather.temperatureString
            self.conditionImageView.image = UIImage(systemName: weather.conditionName)
            self.cityLabel.text = weather.cityName
        }
        
    }
    
    func didFailWithError(error: Error) {
        print(error)
    }
}
 ```
 WeatherManager.swift
```swift
protocol WeatherManagerDelegate {
    func didUpdateWeather(_ weatherManager: WeatherManager, weather: WeatherModel)
    func didFailWithError(error: Error)
}

struct WeatherManager {
    let weatherURL = "[...]"
    
    var delegate: WeatherManagerDelegate?
    
    func performRequest(with urlString: String) {
        //[...]
        delegate?.didFailWithError(error: error!)
        //[...]
    }
 //[...]
 }
 ```
 
#### Using URLSession for Networking
WeatherManager.swift
```swift
    func fetchWeather(cityName: String) {
        let urlString = "\(weatherURL)&q=\(cityName)"
        performRequest(with: urlString)
    }
    
    func fetchWeather(latitude: CLLocationDegrees, longitude: CLLocationDegrees) {
        let urlString = "\(weatherURL)&lat=\(latitude)&lon=\(longitude)"
        performRequest(with: urlString)
    }
    
    func performRequest(with urlString: String) {
        if let url = URL(string: urlString) {
            
            let session = URLSession(configuration: .default)
            
            let task = session.dataTask(with: url) { data, response, error in
                if error != nil {
                    delegate?.didFailWithError(error: error!)
                    return
                }
                if let safeData = data {
                    if let weather = self.parseJSON(safeData) {
                        delegate?.didUpdateWeather(self, weather: weather)
                    }
                }
            }
            
            task.resume()
        }
        
    }
 ```
 
#### Understanding closures
WeatherManager.swift
```swift
func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

func multiply (no1: Int, no2: Int) -> Int {
    return no1 * no2
}

calculator(n1: x, n2: y, operation: multiply)

//This is equal to

func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

calculator(n1: x, n2: y, operation: {(no1, no2) in no1 * no2})

//This is equal to

func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

calculator(n1: x, n2: y,) {$0 * $1}
 ```
 
#### Using Codable protocol for JSON Parsin
WeatherData.swift
```swift
struct WeatherData: Codable {
    let name: String
    let main: Main
    let weather: [Weather]
}

struct Main: Codable {
    let temp: Double
}

struct Weather: Codable {
    let id: Int
    let main: String
    let description: String
    let icon: String
}
 ```
WeatherManager.swift
```swift
    func parseJSON(_ weatherData: Data) -> WeatherModel? {
        let decoder = JSONDecoder()
        
        do {
            let decodedData = try decoder.decode(WeatherData.self, from: weatherData)
            let id = decodedData.weather[0].id
            let temp = decodedData.main.temp
            let name = decodedData.name
            
            let weather = WeatherModel(conditionId: id, cityName: name, temperature: temp)
            return weather
            
        } catch {
            delegate?.didFailWithError(error: error)
            return nil
        }
    }
 ```
 
#### Using Computed Properties
WeatherModel.swift
```swift
struct WeatherModel {
    let conditionId: Int
    let cityName: String
    let temperature: Double
    
    var temperatureString: String {
        return String(format: "%.1f", temperature)
    }
    
    var conditionName: String {
        switch conditionId {
                case 200...232:
                    return "cloud.bolt"
                case 300...321:
                    return "cloud.drizzle"
                case 500...531:
                    return "cloud.rain"
                case 600...622:
                    return "cloud.snow"
                case 701...781:
                    return "cloud.fog"
                case 800:
                    return "sun.max"
                case 801...804:
                    return "cloud.bolt"
                default:
                    return "cloud"
        }
    }
}
 ```
    
</details>    

### BMI Calculator App
![morflax_things-4](https://user-images.githubusercontent.com/49958388/126725617-e3cd6ee2-4e7d-4fed-a9e2-d10e34b5deb3.png)
<details>
    
<summary>See more about BMI Calculator App</summary>
    
#### Understanding the difference between Classes and Structs
```swift
    Struct struct {
        
        let immutable: Any?
        let passedByValue: Any?
    }
    
    Class class {
        
        let inheritance: Any?
        let passedByReference: Any?
    }
 ```

#### Using Segue to pass data between ViewControllers
CalculateViewController.swift
```swift
    @IBAction func calculatePressed(_ sender: UIButton) {
        let height = heightSlider.value
        let weight = weightSlider.value

        calculatorBrain.calculateBMI(height: height, weight: weight)
        
        performSegue(withIdentifier: "goToRsult", sender: self)
    }
    
    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        if segue.identifier == "goToResult" {
            let destinationVC = segue.destination as! ResultViewController
            destinationVC.bmiValue = calculatorBrain.getBMIValue()
            destinationVC.advice = calculatorBrain.getAdvice()
            destinationVC.color = calculatorBrain.getColor()
        }
    }
 ```
 
#### Understanding Optional Binding, Chaining, and Nil Coalescicng
CalculateViewController.swift
```swift
    let foceUnwrapping = optional!
    
    func checkForNilValue() {
        if optional != nil {
            optional!
        }
     }
     
     func optionalBinding() {
        if let safeOptional = optional {
            safeOptional
        }
     }
     
     func nilCoalescingOperator() {
        optional ?? defaultValue
     }
 ```
    
</details>

### Quizzler App
![morflax_things-3](https://user-images.githubusercontent.com/49958388/126725585-12f60320-0031-4f0f-88a1-32528b016720.png)
<details>
    
<summary>See more about Quizzler App</summary>
    
#### Using MVC arquiteture/design pattern
<img width="183" alt="Captura de Tela 2021-07-22 às 16 34 27" src="https://user-images.githubusercontent.com/49958388/126698967-8cb50782-6a08-4410-a645-e04e26252808.png">

#### Using mutating func to update struct atributes
ViewController.swift
```swift
    mutating func nextQuestion() {
        
        if questionNumber + 1 < quiz.count {
            questionNumber += 1
        } else {
            questionNumber = 0
        }
    }
    
    mutating func checkAnswer(userAnswer: String) -> Bool {
        if userAnswer == quiz[questionNumber].answer {
            score += 1
            return true
        } else {
            return false
        }
    }
 ```
    
</details>

### Egg Timer App
![morflax_things-2](https://user-images.githubusercontent.com/49958388/126725505-6e6accd7-5374-493d-bed5-a33868421f96.png)
<details>
    
<summary>See more about Egg Timer App</summary>
    
#### Using Sheduled Timer to set a progress bar
ViewController.swift
```swift
    @IBAction func hardnessSelected(_ sender: UIButton) {
        
        timer.invalidate()
        let hardness = sender.currentTitle!
        totalTime = eggTimes[hardness]!

        progressBar.progress = 0.0
        secondsPassed = 0
        titleLabel.text = hardness

        timer = Timer.scheduledTimer(timeInterval: 1.0, target:self, selector: #selector(updateTimer), userInfo:nil, repeats: true)
    }
    
    @objc func updateTimer() {
        if secondsPassed < totalTime {
            secondsPassed += 1
            progressBar.progress = Float(secondsPassed) / Float(totalTime)
            print(Float(secondsPassed) / Float(totalTime))
        } else {
            timer.invalidate()
            titleLabel.text = "DONE!"
            
            let url = Bundle.main.url(forResource: "alarm_sound", withExtension: "mp3")
            player = try! AVAudioPlayer(contentsOf: url!)
            player.play()
        }
    }
 ```
                                    
</details>
 
### Dicee App 
![morflax_things](https://user-images.githubusercontent.com/49958388/126725345-bb5a9bd4-9ab8-474a-95dc-d1d1d83b5a3e.png)
<details>
    
<summary>See more about Dicee App</summary>
    
#### Using Alignment, Pinning, Containers, Subviews and Stacks to Autolayout
<img width="566" alt="Captura de Tela 2021-07-22 às 16 14 06" src="https://user-images.githubusercontent.com/49958388/126696504-f49c68b0-75ea-41c6-aaa8-ea9f49760554.png">
    
</details>
</details>
</details>
    
<details>
    
<summary>Veja o portfólio em português [PT-BR]</summary>

## Complete IOS App Development Bootcamp Projects
<details>
    
<summary>See more about Complete IOS App Development Bootcamp</summary>

### Advanced Swift Classroom 1
<details>
    
<summary>See more about Advanced Swift Classroom 1</summary>
    
#### Understanding Getters and Setters
```swift
let one: Int = 1

var two: Int {
    get {
        return one + 1
    }
}
 ```
 
```swift
let one: Int = 1

var two: Int {
    set {
        if two != 2 {
            print("two != 2 !!!")
        }
    }
}
 ```
#### Understanding Observed properties
```swift
var one: Int = 1 {
    willSet {
        print("The variable is about to chage")
    }
    didSet {
        print("The variable changed")
    }
}
 ```
    
</details>

### Flash Chat App
![morflax_things-6](https://user-images.githubusercontent.com/49958388/126725712-efa574b9-29ba-44d9-8913-068a135f125c.png)
<details>
    
<summary>See more about Flash Chat App</summary>
    
#### Using Cocoapods to get 3rd party libraries
Podfile
```markdown
platform :ios, '13.0'

target 'Flash Chat iOS13' do

  use_frameworks!

  pod 'CLTypingLabel', '~> 0.4.0'
  pod 'Firebase/Auth'
  pod 'Firebase/Firestore'

end
 ```
 
AppDelegate.swift
```swift
import IQKeyboardManagerSwift

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        // Override point for customization after application launch.
        FirebaseApp.configure()
        Firestore.firestore()
        
        IQKeyboardManager.shared.enable = true
        IQKeyboardManager.shared.enableAutoToolbar = false
        IQKeyboardManager.shared.shouldResignOnTouchOutside = true
        
        return true
    }
//[...]
}
 ```

WelcomeViewController.swift
```swift
@IBOutlet weak var titleLabel: CLTypingLabel!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        titleLabel.text = K.appName
    }
 ```

#### Using Firebase Auth to sign in existing users
LoginViewController.swift
```swift
    @IBAction func loginPressed(_ sender: UIButton) {
        
        if let email = emailTextfield.text, let password = passwordTextfield.text {
            Auth.auth().signIn(withEmail: email, password: password) { [weak self] authResult, error in
                if let e = error {
                    print(e.localizedDescription)
                } else {
                    self!.performSegue(withIdentifier: K.loginSegue, sender: self)
                }
            }
        }
    }
 ```

#### Using Firebase to send chat messages to database
ChatViewController.swift
```swift
    @IBAction func sendPressed(_ sender: UIButton) {
        if let messageBody = messageTextfield.text, let messageSender = Auth.auth().currentUser?.email {
            db.collection(K.FStore.collectionName).addDocument(data: [
                                                                K.FStore.senderField: messageSender,
                                                                K.FStore.bodyField: messageBody,
                                                                K.FStore.dateField: Date().timeIntervalSince1970
            ]) { error in
                if let e = error {
                    print(e)
                } else {
                    print("sendPressed okay")
                    DispatchQueue.main.async {
                        self.messageTextfield.text = ""
                    }
                }
            }
        }
    }
```

#### Using Xib to create a custom TableViewCell
MessageCell.swift
```swift
class MessageCell: UITableViewCell {

    @IBOutlet weak var messageBubble: UIView!
    @IBOutlet weak var label: UILabel!
    @IBOutlet weak var rightImageView: UIImageView!
    @IBOutlet weak var leftImageView: UIImageView!
    
    override func awakeFromNib() {
        super.awakeFromNib()
        
        messageBubble.layer.cornerRadius = messageBubble.frame.size.height / 4
    }

    override func setSelected(_ selected: Bool, animated: Bool) {
        super.setSelected(selected, animated: animated)

        
    }
    
}
```
ChatViewController.swift
```swift
func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        
    let cell = tableView.dequeueReusableCell(withIdentifier: K.cellIdentifier, for: indexPath) as! MessageCell
 //[...]
 }
```
MessageCell.xib

<img width="533" alt="Captura de Tela 2021-07-22 às 19 50 18" src="https://user-images.githubusercontent.com/49958388/126718746-106cc259-de67-42f7-bff3-89b99b952d56.png">

#### Understanding Upcast and Downcast
```swift
    
    let subclassObject = Subclass()
    let classObject = Class()

    if let object = classObject is Subclass {
      let object = classObject as! Subclass
    }
    
    let object = classObject as? Subclass
    
    let object = subclassObject as Class
    
```

#### Understanding ViewController Lifecycle
![image](https://user-images.githubusercontent.com/49958388/126719944-54812cfe-e5b5-4dd5-8927-5f8241778423.png)

#### Understanding App Lifecycle
![image](https://user-images.githubusercontent.com/49958388/126720044-e7b4d813-2d71-46cc-9bec-245e0268f65d.png)
AppDelegate.swift
```swift
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {}

    func application(_ application: UIApplication, configurationForConnecting connectingSceneSession: UISceneSession, options: UIScene.ConnectionOptions) -> UISceneConfiguration {}

    func application(_ application: UIApplication, didDiscardSceneSessions sceneSessions: Set<UISceneSession>) {}
```

SceneDelegate.swift
```swift
    func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {}

    func sceneDidDisconnect(_ scene: UIScene) {}

    func sceneDidBecomeActive(_ scene: UIScene) {}

    func sceneWillResignActive(_ scene: UIScene) {}

    func sceneWillEnterForeground(_ scene: UIScene) {}

    func sceneDidEnterBackground(_ scene: UIScene) {}
```

</details>
    
### Clima App
![morflax_things-5](https://user-images.githubusercontent.com/49958388/126725670-302882be-e602-44a5-a18c-2d198312c165.png)
<details>
    
<summary>See more about Clima App</summary>
    
#### Using Computed Properties
WeatherViewController.swift
```swift
class WeatherViewController: UIViewController {

    @IBOutlet weak var conditionImageView: UIImageView!
    @IBOutlet weak var temperatureLabel: UILabel!
    @IBOutlet weak var cityLabel: UILabel!
    @IBOutlet weak var searchTextField: UITextField!
    
    var weatherManager = WeatherManager()
    let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        locationManager.delegate = self
        weatherManager.delegate = self
        searchTextField.delegate = self
        
        locationManager.requestWhenInUseAuthorization()
        locationManager.requestLocation()
    }
//[...]
}

extension WeatherViewController: CLLocationManagerDelegate {
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        if let location = locations.last {
            locationManager.stopUpdatingLocation()
            let lat = location.coordinate.latitude
            let lon = location.coordinate.longitude
            weatherManager.fetchWeather(latitude: lat, longitude: lon)
        }
    }
    
    func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
        print(error)
    }
}
 ```
 
#### Using CoreLocation to get location data
WeatherViewController.swift
```swift
    let locationManager = CLLocationManager()
    
        override func viewDidLoad() {
            super.viewDidLoad()
            locationManager.delegate = self
            weatherManager.delegate = self
            searchTextField.delegate = self
        
            locationManager.requestWhenInUseAuthorization()
            locationManager.requestLocation()
        }
    
extension WeatherViewController: CLLocationManagerDelegate {
    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        if let location = locations.last {
            locationManager.stopUpdatingLocation()
            let lat = location.coordinate.latitude
            let lon = location.coordinate.longitude
            weatherManager.fetchWeather(latitude: lat, longitude: lon)
        }
    }
    
    func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
        print(error)
    }
}

 ```
 
#### Understanding the Delegate Design pattern and using it to pass data between a model class and ViewController

![image](https://user-images.githubusercontent.com/49958388/126714234-d36d20c2-6852-40a8-94c6-093fd03fccfa.png)
    
WeatherViewController.swift
```swift
class WeatherViewController: UIViewController {
//[...]
    var weatherManager = WeatherManager()
    let locationManager = CLLocationManager()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        locationManager.delegate = self
        weatherManager.delegate = self
        searchTextField.delegate = self
        
        locationManager.requestWhenInUseAuthorization()
        locationManager.requestLocation()
    }
}

extension WeatherViewController: WeatherManagerDelegate {
    func didUpdateWeather(_ weatherManager: WeatherManager, weather: WeatherModel) {
        DispatchQueue.main.async {
            self.temperatureLabel.text = weather.temperatureString
            self.conditionImageView.image = UIImage(systemName: weather.conditionName)
            self.cityLabel.text = weather.cityName
        }
        
    }
    
    func didFailWithError(error: Error) {
        print(error)
    }
}
 ```
 WeatherManager.swift
```swift
protocol WeatherManagerDelegate {
    func didUpdateWeather(_ weatherManager: WeatherManager, weather: WeatherModel)
    func didFailWithError(error: Error)
}

struct WeatherManager {
    let weatherURL = "[...]"
    
    var delegate: WeatherManagerDelegate?
    
    func performRequest(with urlString: String) {
        //[...]
        delegate?.didFailWithError(error: error!)
        //[...]
    }
 //[...]
 }
 ```
 
#### Using URLSession for Networking
WeatherManager.swift
```swift
    func fetchWeather(cityName: String) {
        let urlString = "\(weatherURL)&q=\(cityName)"
        performRequest(with: urlString)
    }
    
    func fetchWeather(latitude: CLLocationDegrees, longitude: CLLocationDegrees) {
        let urlString = "\(weatherURL)&lat=\(latitude)&lon=\(longitude)"
        performRequest(with: urlString)
    }
    
    func performRequest(with urlString: String) {
        if let url = URL(string: urlString) {
            
            let session = URLSession(configuration: .default)
            
            let task = session.dataTask(with: url) { data, response, error in
                if error != nil {
                    delegate?.didFailWithError(error: error!)
                    return
                }
                if let safeData = data {
                    if let weather = self.parseJSON(safeData) {
                        delegate?.didUpdateWeather(self, weather: weather)
                    }
                }
            }
            
            task.resume()
        }
        
    }
 ```
 
#### Understanding closures
WeatherManager.swift
```swift
func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

func multiply (no1: Int, no2: Int) -> Int {
    return no1 * no2
}

calculator(n1: x, n2: y, operation: multiply)

//This is equal to

func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

calculator(n1: x, n2: y, operation: {(no1, no2) in no1 * no2})

//This is equal to

func calculator (n1: Int, n2: Int, operation: (Int, Int) -> Int {
    return operation(n1, n2)
}

calculator(n1: x, n2: y,) {$0 * $1}
 ```
 
#### Using Codable protocol for JSON Parsin
WeatherData.swift
```swift
struct WeatherData: Codable {
    let name: String
    let main: Main
    let weather: [Weather]
}

struct Main: Codable {
    let temp: Double
}

struct Weather: Codable {
    let id: Int
    let main: String
    let description: String
    let icon: String
}
 ```
WeatherManager.swift
```swift
    func parseJSON(_ weatherData: Data) -> WeatherModel? {
        let decoder = JSONDecoder()
        
        do {
            let decodedData = try decoder.decode(WeatherData.self, from: weatherData)
            let id = decodedData.weather[0].id
            let temp = decodedData.main.temp
            let name = decodedData.name
            
            let weather = WeatherModel(conditionId: id, cityName: name, temperature: temp)
            return weather
            
        } catch {
            delegate?.didFailWithError(error: error)
            return nil
        }
    }
 ```
 
#### Using Computed Properties
WeatherModel.swift
```swift
struct WeatherModel {
    let conditionId: Int
    let cityName: String
    let temperature: Double
    
    var temperatureString: String {
        return String(format: "%.1f", temperature)
    }
    
    var conditionName: String {
        switch conditionId {
                case 200...232:
                    return "cloud.bolt"
                case 300...321:
                    return "cloud.drizzle"
                case 500...531:
                    return "cloud.rain"
                case 600...622:
                    return "cloud.snow"
                case 701...781:
                    return "cloud.fog"
                case 800:
                    return "sun.max"
                case 801...804:
                    return "cloud.bolt"
                default:
                    return "cloud"
        }
    }
}
 ```
    
</details>    

### BMI Calculator App
![morflax_things-4](https://user-images.githubusercontent.com/49958388/126725617-e3cd6ee2-4e7d-4fed-a9e2-d10e34b5deb3.png)
<details>
    
<summary>See more about BMI Calculator App</summary>
    
#### Understanding the difference between Classes and Structs
```swift
    Struct struct {
        
        let immutable: Any?
        let passedByValue: Any?
    }
    
    Class class {
        
        let inheritance: Any?
        let passedByReference: Any?
    }
 ```

#### Using Segue to pass data between ViewControllers
CalculateViewController.swift
```swift
    @IBAction func calculatePressed(_ sender: UIButton) {
        let height = heightSlider.value
        let weight = weightSlider.value

        calculatorBrain.calculateBMI(height: height, weight: weight)
        
        performSegue(withIdentifier: "goToRsult", sender: self)
    }
    
    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
        if segue.identifier == "goToResult" {
            let destinationVC = segue.destination as! ResultViewController
            destinationVC.bmiValue = calculatorBrain.getBMIValue()
            destinationVC.advice = calculatorBrain.getAdvice()
            destinationVC.color = calculatorBrain.getColor()
        }
    }
 ```
 
#### Understanding Optional Binding, Chaining, and Nil Coalescicng
CalculateViewController.swift
```swift
    let foceUnwrapping = optional!
    
    func checkForNilValue() {
        if optional != nil {
            optional!
        }
     }
     
     func optionalBinding() {
        if let safeOptional = optional {
            safeOptional
        }
     }
     
     func nilCoalescingOperator() {
        optional ?? defaultValue
     }
 ```
    
</details>

### Quizzler App
![morflax_things-3](https://user-images.githubusercontent.com/49958388/126725585-12f60320-0031-4f0f-88a1-32528b016720.png)
<details>
    
<summary>See more about Quizzler App</summary>
    
#### Using MVC arquiteture/design pattern
<img width="183" alt="Captura de Tela 2021-07-22 às 16 34 27" src="https://user-images.githubusercontent.com/49958388/126698967-8cb50782-6a08-4410-a645-e04e26252808.png">

#### Using mutating func to update struct atributes
ViewController.swift
```swift
    mutating func nextQuestion() {
        
        if questionNumber + 1 < quiz.count {
            questionNumber += 1
        } else {
            questionNumber = 0
        }
    }
    
    mutating func checkAnswer(userAnswer: String) -> Bool {
        if userAnswer == quiz[questionNumber].answer {
            score += 1
            return true
        } else {
            return false
        }
    }
 ```
    
</details>

### Egg Timer App
![morflax_things-2](https://user-images.githubusercontent.com/49958388/126725505-6e6accd7-5374-493d-bed5-a33868421f96.png)
<details>
    
<summary>See more about Egg Timer App</summary>
    
#### Using Sheduled Timer to set a progress bar
ViewController.swift
```swift
    @IBAction func hardnessSelected(_ sender: UIButton) {
        
        timer.invalidate()
        let hardness = sender.currentTitle!
        totalTime = eggTimes[hardness]!

        progressBar.progress = 0.0
        secondsPassed = 0
        titleLabel.text = hardness

        timer = Timer.scheduledTimer(timeInterval: 1.0, target:self, selector: #selector(updateTimer), userInfo:nil, repeats: true)
    }
    
    @objc func updateTimer() {
        if secondsPassed < totalTime {
            secondsPassed += 1
            progressBar.progress = Float(secondsPassed) / Float(totalTime)
            print(Float(secondsPassed) / Float(totalTime))
        } else {
            timer.invalidate()
            titleLabel.text = "DONE!"
            
            let url = Bundle.main.url(forResource: "alarm_sound", withExtension: "mp3")
            player = try! AVAudioPlayer(contentsOf: url!)
            player.play()
        }
    }
 ```
                                    
</details>
 
### Dicee App 
![morflax_things](https://user-images.githubusercontent.com/49958388/126725345-bb5a9bd4-9ab8-474a-95dc-d1d1d83b5a3e.png)
<details>
    
<summary>See more about Dicee App</summary>
    
#### Using Alignment, Pinning, Containers, Subviews and Stacks to Autolayout
<img width="566" alt="Captura de Tela 2021-07-22 às 16 14 06" src="https://user-images.githubusercontent.com/49958388/126696504-f49c68b0-75ea-41c6-aaa8-ea9f49760554.png">
    
</details>
</details>
</details>
