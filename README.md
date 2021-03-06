<h1 align="center"> Hi, I'm Kevin and this is my portfolio (IN PROGRESS)</h1><br/>

![IMG_0091 3](https://user-images.githubusercontent.com/49958388/128245217-30511e86-31e9-4b41-91da-46cfc3b24cec.jpg)

<h6 align="center">๐ง pro.kevinribeiro@gmail.com | ๐ฑ +55 (41) 99635-6430 | ๐ป https://github.com/KevinLittles | ๐ https://www.linkedin.com/in/kevin-ribeiro/</h6>
    
## ๐ Curriculum
<details> 
 
<summary>See more about my curriculum</summary>
<br/>  
    
### Profile   
    
๐ Hello! I'm Kevin, but you can call me Littles if you want. I can summarize myself as an empathetic person, flexible, with great adaptability, and who handles conflicts well. If you want to talk, don't be afraid! Text me right now.

๐ป My area of โโexpertise is mobile development, specifically because of what governs the ecosystem of Apple technologies (such as Swift and IOS). I've already ventured to develop software for watchOS, IpadOS and some other needs that have been appearing in my trajectory like creating a backend with Flask for example.

Today I find myself with these essential tasks:
- ๐ Improve my UI/UX design skills and study more and more Swift in depth and everything that governs such development to become every day an expert dev of the Apple ecosystem, with a focus on mobile.
- ๐ฎ Study the technologies needed to leverage my startup (BuffSpot - Social network made exclusively for gamers), this includes Flutter, AWS, Flask, and everything you can imagine that governs the administration of a company.
- โจ Learn with any type of experience and direct this learning to my soft skills.
    
### Experience
>### ๐ Apple Developer Academy
>#### FEB 2019 - DEC 2020 | PUCPR Curitiba, Brazil
>Over the 2 years of participation, I developed several authored apps alone and in a team. I learned several swift frameworks like UIKit, SpriteKit and ARKit. I learned how to create applications with swift core and healthy programming artifacts like MVC Architecture, Clean Code, some design patterns and code versioning. In addition to code development, I also learned to have a critical view of UX/UI design and thus produce some prototypes before programming an app.
     
    
### Skills
    
| **General Coding Skills** | **Swift Skills** | **Complementary Skills** | **Soft Skills** |
| ------------------------- | ---------------- | -------------------------| ----------------|
| Object Oriented Programming | Storyboards | UX/UI | Empathy
| MVC Architecture | Auto Layout | Figma | Critical sense
| SOLID | Delegate Design Pattern | Sketch | Ease of learning
| Singleton Design pattern | Networking | Advanced english | Adaptation in scenarios
| Consume APIs | JSON Parsing | | Problem solving |
| Firebase Firestore/Auth | Closures | | Good communication |
| Realm | Computed Properties | | Strong emotional intelligence |
| Git/GitFlow | Getters & Setters | | Manage conflicts |
|  | Sheduled Timer | 
|  | Dispatch Queue | 
|  | Extensions | 
|  | Core Location | 
|  | Cocoapods | 
|  | Swift PM | 
|  | Xibs | 
|  | Downcast & Upcast | 
|  | Any, AnyObject, NSObject | 
|  | App Lifecycle | 
|  | ViewController Lifecycle | 
|  | UserDefaults | 
|  | NSCoder | 
|  | Core Data | 
|  | App Publication | 
|  | UIKit |
|  | SpriteKit |
|  | SwiftUI |


       
    
### Education
>### Computer Engeneering
>#### FEB 2016 - DEC 2022 | PUCPR Curitiba, Brazil
>My focus in computer engineering has always been the scope of software development, here I mainly learned about some software engineering principles, imperative and object-oriented programming, data structure, SQL databases and distributed systems (besides of course a lot engineering calculation).

<br/>
    
>### Fundamentals of data science 1
>#### OCT 2017 - JAN 2018 | Udacity
>Project: Analysis of the Bay Area Bike Share Data and extraction of relevant information.
>Technologies: Python 3 with MatPlotLib, Pandas and Numpy.

<br/>
    
>### Many courses
>#### ATEMPORAL | Udemy
>SwiftUI - Learn How to Build Beautiful, Robust, Apps;
>From Beginner to Advanced in Unit Testing on iOS;
>MVVM Design Pattern in SwiftUI;
>Git - The complete course: Git, Github and git-flow.
    
</details>
  
## ๐ฑ Complete IOS App Development Bootcamp Course Projects and Learnings
<details>
    
<summary>See more about Complete IOS App Development Bootcamp</summary>
<br/>

In this course I got, I'm getting and reviewing these (main) following learnings:
    
- Concepts of Object Oriented Programming (OOP): The type system, variables, functions and methods, inheritance, structures, classes and protocols.
- Control Structures: Using If/Else clauses, Switch statements and logic to control the flow of execution.
- Data Structures: How to work with collections, such as arrays and dictionaries.
Software Design: How to organise and format code for readability and how to implement the Model View Controller (MVC) design pattern, Apple's favourite delegation pattern and the publisher pattern.
- Networking: How to make asynchronous API calls, store and retrieve data from the cloud, and use the JSON format for server communication.
- Persistent Local Data Storage: How to use Core Data, Realm, Codable and User Defaults to store your app data locally.
- How to Implement In-App Purchases with Apple StoreKit
- Machine Learning: How to make artificially intelligent apps and build your own machine learning models using iOS 13's new CoreML2 and CreateML frameworks.
- Augmented Reality: How to create 3D objects in augmented reality and create incredible 3D animations and real-life interactions using Apple's latest ARKit2 framework.
- SwiftUI: How to use Apple's brand new UI framework to create user interfaces programmatically that look good across all Apple products.
    
Course link: https://www.udemy.com/course/ios-13-app-development-bootcamp/
### Advanced Swift Classroom 1
<details>
    
<summary>See more about Advanced Swift Classroom 1</summary>
<br/>    
In this first advanced learning session about swift of the course, I understood how the Getters and Setters properties of variables in swift work, in addition I understood how Observed properties work and how I can use them to perform an action once a variable has its value changed or is about to be changed.
    
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
<br/>   
    
The Flash Chat App is a basic chat application with only one global chat!
    
Building the Flash Chat application I learned to:
- Install Cocoapods and use 3rd party libraries
- Use Firebase Auth to register and authenticate a user by email and password
- Use Firebase Firestore to send and load information that was used in the app
- Use .xib files to make a custom UITableViewCell
- Use Downcast and Upcast in swift
- Understand the App and ViewControllers lifecycle

GitHub repository - https://github.com/appbrewery/Flash-Chat-iOS13-Completed
#### Using Cocoapods to get 3rd party libraries
Podfile
```markdown
//[...]
  use_frameworks!

  pod 'CLTypingLabel', '~> 0.4.0'
//[...]
end
 ```
 
AppDelegate.swift
```swift
import IQKeyboardManagerSwift

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        //[...]
        
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

    //[...]
    
    override func awakeFromNib() {
        super.awakeFromNib()
        
    //[...]
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

<img width="533" alt="Captura de Tela 2021-07-22 ร?s 19 50 18" src="https://user-images.githubusercontent.com/49958388/126718746-106cc259-de67-42f7-bff3-89b99b952d56.png">

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
<br/>
The Clima application consists of a weather monitoring app, it uses an API to load data about the local weather (detected by CoreLocation), and having its UI updated as the result.

Building the Clima application I learned to:
- Use Computed Properties to set a variable data
- Use CoreLocation to get location data
- Understand the Delegate Design pattern and using it to pass data between a model class and ViewController
- Use URLSession for Networking
- Understand closures
- Use Codable protocol and JSONDecoder() for JSON Parsing
- Consume an API
- Use DispatchQueue to update the UI elemts in a completion with the main trhead
    
GitHub repository - https://github.com/appbrewery/Clima-iOS13-Completed    
#### Using Computed Properties
WeatherViewController.swift
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
 
#### Using CoreLocation to get location data
WeatherViewController.swift
```swift
    let locationManager = CLLocationManager()
    
        override func viewDidLoad() {
            super.viewDidLoad()
            locationManager.delegate = self
            //[...]
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
 
#### Using Codable protocol and JSONDecoder() for JSON Parsing
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
    
</details>    

### BMI Calculator App
![morflax_things-4](https://user-images.githubusercontent.com/49958388/126725617-e3cd6ee2-4e7d-4fed-a9e2-d10e34b5deb3.png)
<details>
    
<summary>See more about BMI Calculator App</summary>

<br/>
The BMI Calculator application calculates the BMI of a person, based on height and weight

Building the BMI Calculator application I learned to:
- Understand the difference between Classes and Structs
- Use Segue to pass data between ViewControllers
- Understand Optional Binding, Chaining, and Nil Coalescing

GitHub repository - https://github.com/appbrewery/BMI-Calculator-iOS13-Completed
#### Understanding the difference between Classes and Structs
```swift
    Struct struct {
        
        let immutable: true
        let passedByValue: true
    }
    
    Class class {
        
        let inheritance: true
        let passedByReference: true
    }
 ```

#### Using Segue to pass data between ViewControllers
CalculateViewController.swift
```swift
    @IBAction func calculatePressed(_ sender: UIButton) {
        //[...]
        
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
 
#### Understanding Optional Binding, Chaining, and Nil Coalescing
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

<br/>
The Quizzler application is a simple Quiz App!

Building the Quizzler application I learned to:
- Use MVC arquiteture/design pattern
- Use mutating func to update struct atributes   
    
GitHub repository - https://github.com/appbrewery/Quizzler-iOS13-Completed    
#### Using MVC arquiteture/design pattern
<img width="183" alt="Captura de Tela 2021-07-22 ร?s 16 34 27" src="https://user-images.githubusercontent.com/49958388/126698967-8cb50782-6a08-4410-a645-e04e26252808.png">

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

<br/>
The Egg Timer application is an app that shows you how much time remais to your egg get ready to eat!

Building the Egg Timer application I learned to:
- Use Sheduled Timer to set a progress bar
    
GitHub repository - https://github.com/appbrewery/EggTimer-iOS13-Completed    
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

<br/>
The Dicee application is an app that shows you 2 game dices with random values of 1 to 6!

Building the Dicee application I learned to:
- Use Alignment, Pinning, Containers, Subviews and Stacks to Autolayout
 
GitHub repository - https://github.com/appbrewery/Dicee-iOS13-Completed
#### Using Alignment, Pinning, Containers, Subviews and Stacks to Autolayout
<img width="566" alt="Captura de Tela 2021-07-22 ร?s 16 14 06" src="https://user-images.githubusercontent.com/49958388/126696504-f49c68b0-75ea-41c6-aaa8-ea9f49760554.png">
    
</details>
</details>
    
## ๐ Apple Developer Academy Projects and Learnings
<details> 
 
<summary>See more about Apple Developer Academy Projects and Learnings</summary>
<br/>  
  
### Yobaba
![morflax_things-9](https://user-images.githubusercontent.com/49958388/126855974-12ed8b8c-722b-4e73-8d10-c10d9082b859.png)

<details>
    
<summary>See more about Yobaba</summary>

<br/>
The Yobaba app is a mobile story card game develop in SpriteKit. Well, in sum Yobaba tells a history about you and your grandma. The game mecanics is based on arguments... yes, arguments! You and your grandma will have a lot of conversations, and how you will argument your ideia with her is based on cards (that represents differents arguments). This was a work that spent almost 7 months of team work, and I was one of the "code developers" of the project, directly working in the part of SpriteKit developing and the Model classes.
    
In this app I leraned SO MUCH about SpriteKit, a bit about Design, Audio, Storytelling and team work.
    
GitHub repository - https://github.com/KelvinJavorski/Yobaba-Swift-Spritekit   

    
>Weird codes like this have been builded in the main file of SpriteKit Framework ๐จ
```swift
func getCardsFromDiscard (completion: @escaping () -> () = { }) {
        if !gettingCardsFromDiscard {
            let delay = SKAction.wait(forDuration: 0.0)
            let code  = SKAction.run {
                self.i+=1
                Player.shared.getCardFromDiscard(0)
            }
            let sequence = SKAction.sequence([code])
            let loop = SKAction.repeat(sequence, count: Player.shared.discard.cards.count)
            gettingCardsFromDiscard = true
            discardNode.run(loop) {
                self.gettingCardsFromDiscard = false
                for card in Player.shared.deck.cards{
                    print("Card ID no deck: \(card.id)")
                }
                Player.shared.deck.shuffle()
                completion()
            }
        }
    }
```
</details>    
 
### Find The Way
![morflax_things-13](https://user-images.githubusercontent.com/49958388/126880226-ef0e0ce3-ff2c-434a-b93c-c8414647430c.png)

<details>
    
<summary>See more about Find The Way</summary>

<br/>
The Find The Way application is a mobile game developed with SpriteKit! Find The Way consists in a story of a group of tourists that are enjoying their vacation in a island, but one thing that nobody know is that have a murderer in the group. The objetive of the game is to arrive a safe place that the murderer can't do his movements. Everyone in the group have the power to do one movement in the island BUT the tourists dont know where is the safe place, and the murderer knows!
    
Developing this app, i was responsable for coding a big part of SpriteKit and Model classes. I leraned so much about how we can develop an app with UIKit and SpriteKit working togheter and a lot of "mathematical background" in the Models, since we work with a type of "map" for the group of tourists to move around the island. And yes, that was quite complicated to deal with.  
    
GitHub repository - https://github.com/KelvinJavorski/Find-the-Way

</details>
    
</details>   
