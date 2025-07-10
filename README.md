This video, "JavaScript Functions Crash Course" by freeCodeCamp.org, is 1 hour, 36 minutes, and 54 seconds long. It covers a comprehensive range of JavaScript function topics, from fundamentals to advanced concepts like closures and recursion.
Here's a suggested plan to finish the video in 2 days:
Day 1: Fundamentals and Core Concepts (Approx. 48 minutes of video)
 * Watch up to the section on Arrow Functions/Nested Functions/Function Scope. This would cover:
   * Introduction and course overview [00:00:00 - 00:03:17]
   * Fundamentals of JavaScript functions [03:17]
   * Clarifying terminologies (functions vs. methods, parameters vs. arguments) [03:30]
   * Function declarations and executions [03:48]
   * Call stack [03:55]
   * Arrow functions [03:55]
   * Nested functions and function scope [03:55]
 * Review and Practice: After watching, take some time to review the concepts and try out the code examples on your own.
Day 2: Advanced Concepts and Application (Approx. 48 minutes of video)
 * Watch the remainder of the video, starting from Closures. This would cover:
   * Closures [03:59]
   * Callback functions and higher-order functions [03:59]
   * Pure functions [04:03]
   * Immediately Invoked Function Expressions (IIFE) [04:03]
   * Recursion [04:08]
 * Review and Practice: Again, review the concepts and practice implementing them in your own code.
Stand-up Call Details for the Next 2 Days:
Here's a template for your daily stand-up calls, focusing on your progress with the video:
Day 1 Stand-up (e.g., Friday morning):
 * What I did yesterday (or plan to do today): "Today, I plan to watch the first half of the 'JavaScript Functions Crash Course' video, focusing on the fundamentals, function declarations, and arrow functions. I'll also spend time practicing the code examples."
 * What I'll do today (if applicable, for a morning stand-up): (Same as above, or if you already started, describe what you've completed.)
 * What I'll do tomorrow (for an evening stand-up): "Tomorrow, I'll continue with the second half of the video, covering closures, callbacks, and recursion, and then dedicate time to practice."
 * Any blockers: "No blockers currently, but I'll reach out if I get stuck on any of the concepts."
Day 2 Stand-up (e.g., Saturday morning):
 * What I did yesterday: "Yesterday, I completed watching the first half of the 'JavaScript Functions Crash Course' video, covering up to arrow functions and function scope. I also practiced some of the basic function examples."
 * What I'll do today: "Today, I will finish the video by watching the sections on closures, callback functions, pure functions, IIFE, and recursion. My goal is to understand these advanced concepts and then practice implementing them."
 * Any blockers: "No blockers at the moment. I'll focus on understanding the more complex topics today."
Remember to adjust the details based on your actual progress and any challenges you encounter.

Today, I watched the remaining part of the JavaScript video, starting from Closures. It covered closures, callback functions, higher-order functions, pure functions, IIFEs, and recursion. I also continued working on the NRT cases and have almost completed them.
=IF(AND(ISNUMBER(D2), ISNUMBER(E2)), E2 - D2, "")

I’ve started with the basics—focusing on core recommended locators like getByRole, getByText, and getByLabel. I’m also learning how Playwright handles dynamic elements with auto-wait and retry logic. I’ve planned to finish this documentation in 2 days, with hands-on practice to better understand their usage.


@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css');

.main-container {
    min-height: 100vh;
    min-width: 450px;
    font-family: 'calibri';
}

.centered-flex {
    display: flex;
    align-items: center;
    justify-content: center;
}

.form-container {
    width: 400px;
    height: 480px;
    display: grid;
    position: relative;
}

.icon {
    position: absolute;
    width: 85px;
    font-size: 50px;
    display: grid;
    height: 85px;
    place-content: center;
    border: 1px solid #2a2a2a;
    z-index: 1;
    justify-self: center;
    border-radius: 50%;
    background: #0e0e0e;
}

.fa {
    color: #a2a2a2;
}

form {
    flex-direction: column;
    padding: 25px 25px 10px;
    height: 440px;
    border-radius: 30px;
    background: rgba(19, 19, 19, 0.736);
    border: 1px solid rgba(255, 255, 255, 0.097);
    position: absolute;
    width: 100%;
    bottom: 0;
}

.title {
    position: relative;
    margin: 40px 0;
    font-size: 20px;
    font-weight: bold;
    color: white;
}

.msg {
    color: #fa2929;
    position: absolute;
    top: 25%;
}

.field {
    display: flex;
    position: relative;
    width: 100%;
}

.field .fa {
    position: absolute;
    font-size: 14px;
    right: 10px;
    bottom: 10px;
}

input:-webkit-autofill {
    -webkit-box-shadow: 0 0 0 30px rgb(14 14 14) inset;
}

input:-webkit-autofill {
    -webkit-text-fill-color: #bababa !important;
}

form input {
    display: block;
    outline: none;
    width: 100%;
    border: none;
    font-size: 16px;
    color: #d2d2d2;
    margin: 25px 0 5px;
    caret-color: #cccccc;
    background: transparent;
    padding: 10px 25px 3px 0;
    border-bottom: 1px solid #404040;
}

.action {
    justify-content: space-between;
    width: 100%;
    font-size: 14px;
}

.action label {
    cursor: pointer;
    color: #7d7d7d;
}

.action input {
    width: auto;
    margin: 0 8px 0 0;
    cursor: pointer;
}

a {
    text-decoration: none;
    color: #9b9b9b;
}

.btn-container {
    padding: 20px;
    transition: .2s linear;
}

#login-btn {
    padding: 5px 20px;
    border: none;
    background: rgb(25, 62, 97);
    color: white;
    font-weight: 600;
    font-size: 16px;
    border-radius: 15px;
    transition: .3s;
    margin: 25px 0;
}

#login-btn:hover {
    cursor: pointer;
}

.signup {
    color: rgb(70, 70, 70);
    margin-top: 10px;
}

.shift-left {
    transform: translateX(-120%);
}

.shift-right {
    transform: translateX(120%);
}

.shift-top {
    transform: translateY(-150%);
}

.shift-bottom {
    transform: translateY(150%);
}

.no-shift {
    transform: translate(0%, 0%);
}



<div class="main-container centered-flex">
        <div class="form-container">
            <div class="icon fa fa-user"></div>
            <form class="centered-flex">
                <div class="title">LOGIN</div>
                <div class="msg"></div>
                <div class="field">
                    <input type="text" placeholder="Username" id="uname">
                    <span class="fa fa-user"></span>
                </div>
                <div class="field">
                    <input type="password" placeholder="Password" id="pass">
                    <span class="fa fa-lock"></span>
                </div>
                <div class="action centered-flex">
                    <label for="remember" class="centered-flex">
                        <input type="checkbox" id="remember"> Remember me
                    </label>
                    <a href="#">Forget Password ?</a>
                </div>
                <div class="btn-container">
                    <input type="submit" id="login-btn" value="Login">
                </div>
                <div class="signup">Don't have an Account?<a href="#"> Sign up</a></div>
            </form>
        </div>
</div>

const uname = document.querySelector('#uname');
const pass = document.querySelector('#pass');
const btnContainer = document.querySelector('.btn-container');
const btn = document.querySelector('#login-btn');
const form = document.querySelector('form');
const msg = document.querySelector('.msg');
btn.disabled = true;

function shiftButton() {
    showMsg();
    const positions = ['shift-left', 'shift-top', 'shift-right', 'shift-bottom'];
    const currentPosition = positions.find(dir => btn.classList.contains(dir));
    const nextPosition = positions[(positions.indexOf(currentPosition) + 1) % positions.length];
    btn.classList.remove(currentPosition);
    btn.classList.add(nextPosition);
}

function showMsg() {
    const isEmpty = uname.value === '' || pass.value === '';
    btn.classList.toggle('no-shift', !isEmpty);

    if (isEmpty) {
        btn.disabled = true
        msg.style.color = 'rgb(218 49 49)';
        msg.innerText = 'Please fill the input fields before proceeding';
    } else {
        msg.innerText = 'Great! Now you can proceed';
        msg.style.color = '#92ff92';
        btn.disabled = false;
        btn.classList.add('no-shift')
    }
}

btnContainer.addEventListener('mouseover', shiftButton);
btn.addEventListener('mouseover', shiftButton);
form.addEventListener('input', showMsg)
btn.addEventListener('touchstart', shiftButton);


