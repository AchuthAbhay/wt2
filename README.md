# wt2 
<h2>Login</h2>
<div class="login">
  <form (ngSubmit)="login()">
  <div class="useranme"> 
    <label>
    Username:
    <input type="text" [(ngModel)]="username" name="username" required>
  </label>
</div>
<div class="password">
  <label >
 
  Password:
    <input type="password" [(ngModel)]="password" name="password" required>
  </label>
</div>
<div>
  <button type="submit">Login</button>
</div>
  
</form>

 
</div>
#ts
import { Component } from '@angular/core';
import { AuthService } from '../auth.service';

@Component({
  selector: 'app-login',
  templateUrl: './login.component.html'
})
export class LoginComponent {
  username: string = '';
  password: string = '';

  constructor(private authService: AuthService) {}

  login() {
    if (this.authService.login(this.username, this.password)) {
      alert('Login successful!');
    } else {
      alert('Login failed.');
    }
  }
}
#registration
<h2>Register</h2>
<form (ngSubmit)="register()">
  <label>
    Username:
    <input type="text" [(ngModel)]="username" name="username" required>
  </label>
  <label>
    Password:
    <input type="password" [(ngModel)]="password" name="password" required>
  </label>
  <button type="submit">Register</button>
</form>
#ts
import { Component } from '@angular/core';
import { AuthService } from '../auth.service';

@Component({
  selector: 'app-register',
  templateUrl: './register.component.html'
})
export class RegisterComponent {
  username: string = '';
  password: string = '';

  constructor(private authService: AuthService) {}

  register() {
    if (this.authService.register(this.username, this.password)) {
      alert('Registration successful!');
    } else {
      alert('Registration failed.');
    }
  }
}
#ng serve ,npm install -g @angular/cli,ng new <project-name>
