# Chal-3
NOTE: I did work with a tutor on this for guidance
A password generator

# Password Generator Starter Code

// Assignment code here


// Get references to the #generate element
var generateBtn = document.querySelector("#generate");

// Write password to the #password input
function writePassword() {
  var password = generatePassword();
  var passwordText = document.querySelector("#password");

  passwordText.value = password;

}

// Add event listener to generate button
generateBtn.addEventListener("click", writePassword);


// Fixed code

// Assignment code here
function generatePassword() {
  const upperCase = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  const lowerCase = "abcdefghijklmnopqrstuvwxyz";
  const numbers = "0123456789";
  const special = "!@#$%^&_-+()";
  let pool = "";

  const length = prompt("Enter the desired length of the password (between 8 and 128):");
  if (isNaN(length) || length < 8 || length > 128) {
    alert("Invalid length. Please enter a number between 8 and 128.");
    return "";
  }

  const includeUpperCase = confirm("Include uppercase letters?");
  const includeLowerCase = confirm("Include lowercase letters?");
  const includeNumbers = confirm("Include numbers?");
  const includeSpecial = confirm("Include special characters?");

  if (!includeUpperCase && !includeLowerCase && !includeNumbers && !includeSpecial) {
    alert("At least one character type must be selected.");
    return "";
  }

  if (includeUpperCase) {
    pool += upperCase;
  }
  if (includeLowerCase) {
    pool += lowerCase;
  }
  if (includeNumbers) {
    pool += numbers;
  }
  if (includeSpecial) {
    pool += special;
  }

  let password = "";
  for (let i = 0; i < length; i++) {
    const randomIndex = Math.floor(Math.random() * pool.length);
    password += pool[randomIndex];
  }

  return password;
}

// Get references to the #generate element
var generateBtn = document.querySelector("#generate");


// Write password to the #password input
function writePassword() {
  var password = generatePassword();
  var passwordText = document.querySelector("#password");

  passwordText.value = password;
}


// Add event listener to generate button
generateBtn.addEventListener("click", writePassword);
