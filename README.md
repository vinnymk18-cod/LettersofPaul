<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INSIGHT FOR CHRIST</title>
    <style>
        :root {
            --lavender-bg: #E6E6FA;
            --lavender-light: #F3F3FF;
            --lavender-dark: #D1D1FA;
            --button-green: #90EE90;
            --button-green-hover: #7CCD7C;
            --text-black: #000000;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--text-black);
        }

        body {
            background-color: var(--lavender-bg);
            /* Soft, non-distracting floral wallpaper pattern using CSS vectors */
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(225, 190, 231, 0.4) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(225, 190, 231, 0.4) 0%, transparent 20%),
                radial-gradient(circle at 50% 50%, rgba(243, 229, 245, 0.3) 0%, transparent 40%);
            background-attachment: fixed;
            background-size: cover;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .container {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 30px;
            width: 100%;
            max-width: 900px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.18);
            display: none;
            position: relative;
        }

        .container.active {
            display: block;
        }

        h1, h2, h3, h4 {
            text-align: center;
            margin-bottom: 20px;
            font-weight: 700;
        }

        h1 { font-size: 2.5rem; color: #4A154B; }

        p {
            margin-bottom: 15px;
            line-height: 1.6;
        }

        .btn {
            display: inline-block;
            background-color: var(--button-green);
            padding: 12px 24px;
            border: 2px solid var(--text-black);
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            font-size: 1rem;
            transition: all 0.3s ease;
            text-align: center;
            text-decoration: none;
            margin: 10px 5px;
        }

        .btn:hover {
            background-color: var(--button-green-hover);
            transform: translateY(-2px);
        }

        .btn-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin-top: 20px;
        }

        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            border-top: 1px solid var(--lavender-dark);
            padding-top: 20px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }

        input[type="text"], input[type="email"], input[type="password"], textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid var(--lavender-dark);
            border-radius: 8px;
            background: var(--lavender-light);
            font-size: 1rem;
        }

        input:focus, textarea:focus {
            outline: none;
            border-color: #4A154B;
        }

        /* Table Styling */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background: white;
            border-radius: 8px;
            overflow: hidden;
        }

        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid var(--lavender-dark);
        }

        th {
            background-color: var(--lavender-dark);
            font-weight: bold;
        }

        tr:hover {
            background-color: var(--lavender-light);
        }

        /* Study Guide Layout */
        .verse-box {
            background: rgba(255, 255, 255, 0.9);
            border-left: 4px solid #4A154B;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 0 8px 8px 0;
        }

        .section-block {
            background: var(--lavender-light);
            padding: 20px;
            border-radius: 10px;
            margin-top: 25px;
            border: 1px solid var(--lavender-dark);
        }

        .section-block h3 {
            text-align: left;
            color: #4A154B;
            border-bottom: 2px solid var(--button-green);
            padding-bottom: 5px;
        }
    </style>
</head>
<body>

    <div id="page-home" class="container active">
        <h1>INSIGHT FOR CHRIST🤗</h1>
        <p style="text-align: center; font-size: 1.2rem;">Welcome to your digital deep-dive into the Holy Scriptures. Grow, learn, and track your spiritual journey systematically.</p>
        <div class="btn-container">
            <button class="btn" onclick="navigateTo('page-gate')">Sign up</button>
        </div>
    </div>

    <div id="page-gate" class="container">
        <h2>Choose Your Account Type</h2>
        <div class="btn-container">
            <button class="btn" onclick="navigateTo('page-admin-login')">Log in as Admin</button>
            <button class="btn" onclick="navigateTo('page-user-register')">Log in as User</button>
        </div>
        <div class="nav-buttons">
            <button class="btn" onclick="navigateBack()">Back</button>
        </div>
    </div>

    <div id="page-admin-login" class="container">
        <h2>Admin Authentication</h2>
        <div class="form-group">
            <label for="admin-email">Admin Email Address</label>
            <input type="email" id="admin-email" placeholder="enter admin email...">
        </div>
        <div class="form-group">
            <label for="admin-password">Admin Password</label>
            <input type="password" id="admin-password" placeholder="enter password...">
        </div>
        <div class="btn-container">
            <button class="btn" onclick="validateAdmin()">Done</button>
        </div>
        <div class="nav-buttons">
            <button class="btn" onclick="navigateBack()">Back</button>
        </div>
    </div>

    <div id="page-admin-dashboard" class="container">
        <h2>Admin Management Dashboard</h2>
        <p><strong>Tracking Panel:</strong> Review user progress and insert feedback instantly.</p>
        <div style="overflow-x: auto;">
            <table>
                <thead>
                    <tr>
                        <th>Username</th>
                        <th>Email</th>
                        <th>Current Progress</th>
                        <th>Admin Feedback/Comments</th>
                        <th>Action</th>
                    </tr>
                </thead>
                <tbody id="admin-table-body">
                    </tbody>
            </table>
        </div>
        <div class="nav-buttons">
            <button class="btn" onclick="navigateBack()">Back</button>
        </div>
    </div>

    <div id="page-user-register" class="container">
        <h2>User Account Setup</h2>
        <div class="form-group">
            <label for="user-username">Username</label>
            <input type="text" id="user-username" placeholder="Choose a username...">
        </div>
        <div class="form-group">
            <label for="user-email">Email Address</label>
            <input type="email" id="user-email" placeholder="Your email address...">
        </div>
        <div class="form-group">
            <label for="user-password">Password</label>
            <input type="password" id="user-password" placeholder="Create your private password...">
        </div>
        <div class="btn-container">
            <button class="btn" onclick="registerUser()">Log in</button>
        </div>
        <div class="nav-buttons">
            <button class="btn" onclick="navigateBack()">Back</button>
        </div>
    </div>

    <div id="page-user-welcome" class="container">
        <h2>WELCOME TO THE GOSPEL OF GALATIANS</h2>
        <p style="text-align: center;">Prepare your heart to study the profound freedom we possess in Christ Jesus through Paul’s letter to the Galatians churches.</p>
        <div class="btn-container">
            <button class="btn" onclick="startStudy()">Start</button>
        </div>
        <div class="nav-buttons">
            <button class="btn" onclick="navigateBack()">Back</button>
        </div>
    </div>

    <div id="page-study" class="container">
        <h2 id="study-title">Galatians Chapter X</h2>
        
        <div id="study-content">
            </div>

        <div class="section-block">
            <h3>Learning Outcomes / Objectives</h3>
            <p id="study-outcomes"></p>
        </div>

        <div class="section-block">
            <h3>Detailed Lessons Learnt</h3>
            <p id="study-lessons"></p>
        </div>

        <div class="section-block">
            <h3>Practical Application of Lessons</h3>
            <p id="study-applications"></p>
        </div>

        <div class="section-block">
            <h3>Reflection Questions & Journaling</h3>
            <div id="study-questions"></div>
        </div>

        <div class="nav-buttons">
            <button class="btn" id="study-prev-btn" onclick="prevChapter()">Previous Chapter</button>
            <button class="btn" onclick="navigateBack()">Back</button>
            <button class="btn" id="study-next-btn" onclick="nextChapter()">Next / Save Progress</button>
        </div>
    </div>

    <script>
        // --- DATA & CONTENT REPOSITORY ---
        const galatiansData = {
            1: {
                title: "Galatians Chapter 1: Defending the True Gospel",
                verses: [
                    "vv. 1-5: Paul asserts his divine apostolic calling, greeting them with grace/peace.",
                    "vv. 6-10: Paul expresses shock that they are deserting God for a distorted gospel. He states explicitly: if anyone preaches a gospel contrary to the truth, let them be accursed.",
                    "vv. 11-24: Paul traces his testimony, proving his message came directly via revelation from Jesus Christ, not humans."
                ],
                outcomes: "Understand the divine origin of the true gospel; distinguish clearly between structural legalism and pure grace; appreciate how an encounter with Christ completely changes a human story.",
                lessons: "There is exactly one authentic saving gospel: salvation entirely by grace through faith in Jesus Christ alone. Adding human checklist requirements voids the message. Furthermore, God can take the greatest enemy of the church and instantly convert them into a foundational structural tool for His Kingdom.",
                applications: "Guard your heart daily against 'performance-based' theology. Refuse to change structural Christian truths just to win cultural approval or avoid conflict. Continually share your testimony with people so others see God's transforming power active inside your lifestyle.",
                questions: ["In what subtle formats do we try to add human performance to God's grace today?", "Is there an area in your current network where you are compromising truths to stay popular?"]
            },
            2: {
                title: "Galatians Chapter 2: Crucified with Christ",
                verses: [
                    "vv. 1-10: Church leadership in Jerusalem confirms Paul's structural assignment to the Gentiles.",
                    "vv. 11-14: Paul openly confronts Peter in Antioch for acting hypocritically by pulling away from eating with Gentiles when legalistic critics arrived.",
                    "vv. 15-21: Declares humanity is justified solely by faith in Jesus Christ, not by the legal works of the law."
                ],
                outcomes: "Grasp structural unity among believers across distinct cultures; realize the danger of spiritual hypocrisy; articulate the definition of justification by faith.",
                lessons: "Peer pressure can cause even mature believers to act hypocritically if they lose focus on the gospel. True justification means God looks at us through Christ's righteousness. We don't clean ourselves up to approach Him; he makes us clean.",
                applications: "Be prepared to gently yet firmly stand up for gospel truths, even if prominent leaders waver. Identify if you treat certain believers as secondary due to social status or backgrounds. Declare daily: 'I am crucified with Christ; it is no longer I who live, but Christ lives inside me.'",
                questions: ["Have you ever compromised scriptural principles to fit into a religious or social crowd?", "What does it look like practically in your schedule to live dynamically 'crucified with Christ'?"]
            },
            3: {
                title: "Galatians Chapter 3: Faith vs. Law Performance",
                verses: [
                    "vv. 1-5: Paul calls them foolish, asking if they received the Holy Spirit by following the law or by believing what they heard.",
                    "vv. 6-14: Cites Abraham as the ultimate example of faith. Explains Christ redeemed us completely from the curse of the law by becoming a curse for us on the tree.",
                    "vv. 15-29: Explains the law acted as a temporary guardian leading us to Christ, making us all children of God through faith."
                ],
                outcomes: "Recognize Abraham's historical justification by faith; identify the purpose of the Old Testament law; see yourself as an heir to the divine promise.",
                lessons: "The law was meant to expose our deep need for a Savior, acting like a strict school teacher. Once faith arrives, we transition into mature family status. Through baptism into Christ, all worldly demographic divisions vanish—we are unified as heirs of Abraham.",
                applications: "Stop trying to finish in human strength what God started with the Holy Spirit. When guilt from past failure attacks, remember Christ completely absorbed your curse on the cross. Treat every believer as an absolute equal, breaking down racial or socioeconomic barriers.",
                questions: ["Are you trying to sustain your spiritual walk via rules or via active reliance on the Holy Spirit?", "How does knowing you are a full legal heir to God change your daily confidence level?"]
            },
            4: {
                title: "Galatians Chapter 4: No Longer Slaves, But Children",
                verses: [
                    "vv. 1-7: God sent His Son at the perfect historical time to redeem those under the law, adopting us so we can cry out 'Abba, Father!'",
                    "vv. 8-20: Paul worries about them returning to elementary spiritual slavery and details his deep personal love for them.",
                    "vv. 21-31: Uses the allegorical illustration of Sarah (freedom/promise) versus Hagar (slavery/flesh)."
                ],
                outcomes: "Articulate the deep structural shift from slavery to adoption; recognize the security of a child of God; understand the distinct allegorical lines of flesh vs promise.",
                lessons: "Believers are not slaves trying to earn an inheritance; we are children who already possess it. Returning to religious checklists is like a free citizen volunteering to go back inside a prison cell. God desires an intimate relationship ('Abba') rather than cold religious distance.",
                applications: "When you pray, deliberately address God with the confidence of an adopted child approaching a loving father. Actively audit your routine to remove legalistic mechanisms that rob you of spiritual joy. Build deep personal investment into your discipleship relationships.",
                questions: ["Do you find yourself treating God like an angry taskmaster or a loving Father?", "What are the 'weak and worthless elementary principles' you find yourself tempted to slide back into?"]
            },
            5: {
                title: "Galatians Chapter 5: Freedom and Walking in the Spirit",
                verses: [
                    "vv. 1-12: Standard call to hold fast to freedom, warning that relying on circumcision cuts someone off from the operational grace of Christ.",
                    "vv. 13-15: Cautions against using freedom as an excuse for sinful indulgence, commanding instead to serve one another in love.",
                    "vv. 16-26: Details the violent internal conflict between the flesh and the Spirit. Contrasts the works of the flesh with the structural Fruit of the Spirit."
                ],
                outcomes: "Define true Christian freedom; contrast the works of the flesh with spiritual fruit; establish the methodology for walking systematically in the Spirit.",
                lessons: "Christian freedom isn't the license to do whatever our old nature wants; it's the empowerment to finally live the way God designed us to live. Producing holy character doesn't happen by trying harder to follow rules, but by choosing to yield to the Holy Spirit's promptings daily.",
                applications: "When tempted, consciously hand that specific moment over to the Holy Spirit. Cultivate love, joy, and peace by remaining connected to Jesus. Actively crucify negative impulses like jealousy, bursts of anger, or division as soon as they spark.",
                questions: ["Which specific element of the Fruit of the Spirit do you feel needs major growth in your life right now?", "How can you tell the difference between utilizing your freedom for love versus using it for selfish fleshly desires?"]
            },
            6: {
                title: "Galatians Chapter 6: Doing Good to All",
                verses: [
                    "vv. 1-5: Instructions on gently restoring a brother caught in sin, bearing one another's structural burdens.",
                    "vv. 6-10: Describes the universal law of sowing and reaping. Explains that sowing to the Spirit reaps eternal life, so we must not grow weary.",
                    "vv. 11-18: Paul makes a final structural declaration: boasting only in the cross of Christ, emphasizing a transformed new creation over external rituals."
                ],
                outcomes: "Implement compassionate restoration within fellowship; apply the principle of spiritual sowing and reaping; ground your identity strictly in the cross.",
                lessons: "We are called to carry each other's heavy crises while remaining accountable for our own daily responsibilities. Spiritual life functions like farming: what you plant determines what you harvest. External rituals mean nothing; a completely transformed heart is what counts.",
                applications: "Look for someone struggling under a heavy burden this week and find a concrete way to assist them. Keep doing good and volunteering, even if you feel tired, knowing the harvest is coming. Refuse to boast about personal accomplishments; let your identity rest in Christ's cross.",
                questions: ["Who around you is currently overwhelmed and needs you to help carry their burden?", "What are you primarily planting into your mind and heart daily—things of the flesh or things of the Spirit?"]
            }
        };

        // --- STATE MANAGEMENT SYSTEM (Simulation of real-time multi-device storage) ---
        let pageHistory = [];
 
# LettersofPaul
Studying the book of Galatians 
