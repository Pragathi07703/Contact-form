# Contact-form
#html file
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Form with Validation</title>
    <link rel="stylesheet" href="form-styles.css">
</head>
<body>
    <div class="container">
        <header>
            <h1>Contact Us</h1>
            <p>Fill out the form below and we'll get back to you!</p>
        </header>

        <main>
            <form id="contact-form" novalidate>
                <div class="form-group">
                    <label for="name">Full Name *</label>
                    <input type="text" id="name" name="name" required>
                    <span class="error-message" id="name-error"></span>
                </div>

                <div class="form-group">
                    <label for="email">Email Address *</label>
                    <input type="email" id="email" name="email" required>
                    <span class="error-message" id="email-error"></span>
                </div>

                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone">
                    <span class="error-message" id="phone-error"></span>
                </div>

                <div class="form-group">
                    <label for="subject">Subject *</label>
                    <select id="subject" name="subject" required>
                        <option value="">Choose a subject</option>
                        <option value="general">General Inquiry</option>
                        <option value="support">Technical Support</option>
                        <option value="feedback">Feedback</option>
                        <option value="other">Other</option>
                    </select>
                    <span class="error-message" id="subject-error"></span>
                </div>

                <div class="form-group">
                    <label for="message">Message *</label>
                    <textarea id="message" name="message" rows="5" required></textarea>
                    <span class="error-message" id="message-error"></span>
                </div>

                <div class="form-group">
                    <label class="checkbox-label">
                        <input type="checkbox" id="newsletter" name="newsletter">
                        Subscribe to our newsletter
                    </label>
                </div>

                <button type="submit" id="submit-btn">Send Message</button>
            </form>

            <div id="success-message" class="hidden">
                <h3>Thank you for your message!</h3>
                <p>We'll get back to you within 24 hours.</p>
            </div>
        </main>

        <section id="todo-section">
            <h2>Dynamic To-Do List</h2>
            <div class="todo-container">
                <input type="text" id="todo-input" placeholder="Add a new task...">
                <button id="add-todo">Add Task</button>
                <ul id="todo-list"></ul>
            </div>
        </section>
    </div>

    <script src="form-script.js"></script>

#css file
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    padding: 20px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    background: white;
    border-radius: 15px;
    box-shadow: 0 15px 35px rgba(0,0,0,0.1);
    overflow: hidden;
}

header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    padding: 40px;
    text-align: center;
}

header h1 {
    font-size: 2.5rem;
    margin-bottom: 10px;
}

main {
    padding: 40px;
}

.form-group {
    margin-bottom: 25px;
}

label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #333;
}

input[type="text"],
input[type="email"],
input[type="tel"],
select,
textarea {
    width: 100%;
    padding: 12px 15px;
    border: 2px solid #e1e1e1;
    border-radius: 8px;
    font-size: 16px;
    transition: border-color 0.3s ease;
}

input:focus,
select:focus,
textarea:focus {
    outline: none;
    border-color: #667eea;
}

input.error,
select.error,
textarea.error {
    border-color: #e74c3c;
}

.error-message {
    color: #e74c3c;
    font-size: 14px;
    margin-top: 5px;
    display: block;
}

.checkbox-label {
    display: flex;
    align-items: center;
    cursor: pointer;
}

.checkbox-label input {
    width: auto;
    margin-right: 10px;
}

#submit-btn {
    width: 100%;
    padding: 15px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: none;
    border-radius: 8px;
    font-size: 18px;
    font-weight: 600;
    cursor: pointer;
    transition: transform 0.2s ease;
}

#submit-btn:hover {
    transform: translateY(-2px);
}

#success-message {
    text-align: center;
    color: #27ae60;
    padding: 30px;
    background: #ecf0f1;
    border-radius: 8px;
    margin-top: 20px;
}

.hidden {
    display: none;
}

/* Todo Section Styles */
#todo-section {
    padding: 40px;
    background: #f8f9fa;
}

#todo-section h2 {
    color: #333;
    margin-bottom: 20px;
    text-align: center;
}

.todo-container {
    max-width: 500px;
    margin: 0 auto;
}

#todo-input {
    width: calc(100% - 120px);
    margin-right: 10px;
}

#add-todo {
    width: 100px;
    padding: 12px;
    background: #667eea;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

#todo-list {
    list-style: none;
    margin-top: 20px;
}

.todo-item {
    background: white;
    margin: 10px 0;
    padding: 15px;
    border-radius: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.delete-btn {
    background: #e74c3c;
    color: white;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
}

/* Responsive Design */
@media (max-width: 768px) {
    .container {
        margin: 10px;
    }
    
    header {
        padding: 20px;
    }
    
    header h1 {
        font-size: 2rem;
    }
    
    main, #todo-section {
        padding: 20px;
    }
    
    #todo-input {
        width: 100%;
        margin-bottom: 10px;
    }
    
    #add-todo {
        width: 100%;
    }
}

#JS file
class FormValidator {
    constructor() {
        this.form = document.getElementById('contact-form');
        this.submitBtn = document.getElementById('submit-btn');
        this.successMessage = document.getElementById('success-message');
        this.initEventListeners();
        this.initTodoList();
    }

    initEventListeners() {
        this.form.addEventListener('submit', (e) => this.handleSubmit(e));
        
        // Real-time validation
        const inputs = this.form.querySelectorAll('input, select, textarea');
        inputs.forEach(input => {
            input.addEventListener('blur', () => this.validateField(input));
            input.addEventListener('input', () => this.clearError(input));
        });
    }

    handleSubmit(e) {
        e.preventDefault();
        const isValid = this.validateForm();
        
        if (isValid) {
            this.showSuccess();
        }
    }

    validateForm() {
        let isValid = true;
        const fields = ['name', 'email', 'subject', 'message'];
        
        fields.forEach(fieldName => {
            const field = document.getElementById(fieldName);
            if (!this.validateField(field)) {
                isValid = false;
            }
        });
        
        return isValid;
    }

    validateField(field) {
        const value = field.value.trim();
        const fieldName = field.name;
        let isValid = true;
        let errorMessage = '';

        // Clear previous errors
        this.clearError(field);

        switch(fieldName) {
            case 'name':
                if (!value) {
                    errorMessage = 'Name is required';
                    isValid = false;
                } else if (value.length < 2) {
                    errorMessage = 'Name must be at least 2 characters';
                    isValid = false;
                }
                break;

            case 'email':
                const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                if (!value) {
                    errorMessage = 'Email is required';
                    isValid = false;
                } else if (!emailRegex.test(value)) {
                    errorMessage = 'Please enter a valid email address';
                    isValid = false;
                }
                break;

            case 'phone':
                if (value && !/^\d{10}$/.test(value.replace(/\D/g, ''))) {
                    errorMessage = 'Please enter a valid 10-digit phone number';
                    isValid = false;
                }
                break;

            case 'subject':
                if (!value) {
                    errorMessage = 'Please select a subject';
                    isValid = false;
                }
                break;

            case 'message':
                if (!value) {
                    errorMessage = 'Message is required';
                    isValid = false;
                } else if (value.length < 10) {
                    errorMessage = 'Message must be at least 10 characters';
                    isValid = false;
                }
                break;
        }

        if (!isValid) {
            this.showError(field, errorMessage);
        }

        return isValid;
    }

    showError(field, message) {
        field.classList.add('error');
        const errorElement = document.getElementById(`${field.name}-error`);
        if (errorElement) {
            errorElement.textContent = message;
        }
    }

    clearError(field) {
        field.classList.remove('error');
        const errorElement = document.getElementById(`${field.name}-error`);
        if (errorElement) {
            errorElement.textContent = '';
        }
    }

    showSuccess() {
        this.form.style.display = 'none';
        this.successMessage.classList.remove('hidden');
        
        // Reset form after 3 seconds
        setTimeout(() => {
            this.form.reset();
            this.form.style.display = 'block';
            this.successMessage.classList.add('hidden');
        }, 3000);
    }

    // Todo List Functionality
    initTodoList() {
        this.todoInput = document.getElementById('todo-input');
        this.addBtn = document.getElementById('add-todo');
        this.todoList = document.getElementById('todo-list');
        this.todos = [];

        this.addBtn.addEventListener('click', () => this.addTodo());
        this.todoInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') this.addTodo();
        });
    }

    addTodo() {
        const todoText = this.todoInput.value.trim();
        if (!todoText) return;

        const todo = {
            id: Date.now(),
            text: todoText,
            completed: false
        };

        this.todos.push(todo);
        this.renderTodos();
        this.todoInput.value = '';
    }

    removeTodo(id) {
        this.todos = this.todos.filter(todo => todo.id !== id);
        this.renderTodos();
    }

    renderTodos() {
        this.todoList.innerHTML = '';
        
        this.todos.forEach(todo => {
            const todoItem = document.createElement('li');
            todoItem.className = 'todo-item';
            todoItem.innerHTML = `
                <span>${todo.text}</span>
                <button class="delete-btn" onclick="validator.removeTodo(${todo.id})">Delete</button>
            `;
            this.todoList.appendChild(todoItem);
        });
    }
}

// Initialize the form validator
const validator = new FormValidator();
</body>
</html>
