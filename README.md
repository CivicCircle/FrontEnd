# CivicCircle FrontEnd

Building Community, Empowering Volunteers. This repository houses the user interface that connects volunteers to impactful civic opportunities, enhancing engagement through intuitive design and seamless functionality.

## Table of Contents

- [CivicCircle FrontEnd](#civiccircle-frontend)
  - [Table of Contents](#table-of-contents)
  - [Project Structure](#project-structure)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Running the Server](#running-the-server)
  - [Usage](#usage)
  - [Routes](#routes)
    - [Organization Routes](#organization-routes)
    - [Volunteer Routes](#volunteer-routes)
    - [Authentication Routes](#authentication-routes)
  - [Templates](#templates)
  - [Static Files](#static-files)
  - [Contributing](#contributing)
  - [License](#license)

## Project Structure

```
/home/ranuga/Programming/Projects/All/CivicCircle/FrontEnd/
├── .gitignore
├── LICENSE
├── README.md
├── app.py
├── requirements.txt
├── server
│   ├── __init__.py
│   ├── api
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── home.py
│   │   ├── organization.py
│   │   ├── volunteer.py
│   ├── helper_functions.py
│   ├── routes
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── home.py
│   │   ├── organization.py
│   │   ├── volunteer.py
│   ├── static
│   │   ├── images
│   │   │   └── logo.jpg
│   │   ├── scripts
│   │   │   ├── home
│   │   │   │   ├── about_us.js
│   │   │   │   ├── base.js
│   │   │   │   ├── contact_us.js
│   │   │   │   ├── login.js
│   │   │   │   └── sign_up.js
│   │   │   ├── organization
│   │   │   │   ├── trainings.js
│   │   │   │   └── volunteers.js
│   │   ├── styles
│   │   │   ├── admin
│   │   │   │   └── base.css
│   │   │   ├── errors
│   │   │   │   ├── 404.css
│   │   │   │   └── 500.css
│   │   │   ├── home
│   │   │   │   ├── about_us.css
│   │   │   │   ├── base.css
│   │   │   │   ├── contact_us.css
│   │   │   │   ├── home.css
│   │   │   │   ├── login.css
│   │   │   ├── organization
│   │   │   │   ├── applicants.css
│   │   │   │   ├── base.css
│   │   │   │   ├── trainings.css
│   │   │   │   └── volunteer_resume_analysitation.css
│   │   │   ├── volunteer
│   │   │   │   └── base.css
│   ├── templates
│   │   ├── admin
│   │   │   ├── admin
│   │   │   │   ├── ban.html
│   │   │   │   ├── base.html
│   │   │   │   ├── blog_writing.html
│   │   │   │   ├── home.html
│   │   │   │   ├── membership_requests.html
│   │   │   │   └── social_media.html
│   │   │   ├── ban.html
│   │   │   ├── base.html
│   │   │   ├── blog_writing.html
│   │   │   ├── home.html
│   │   │   ├── membership_requests.html
│   │   │   ├── social_media.html
│   │   ├── errors
│   │   │   ├── 404.html
│   │   │   └── 500.html
│   │   ├── home
│   │   │   ├── about_us.html
│   │   │   ├── base.html
│   │   │   ├── contact_us.html
│   │   │   ├── home.html
│   │   │   ├── login.html
│   │   │   └── sign_up.html
│   │   ├── organization
│   │   │   ├── applicants.html
│   │   │   ├── base.html
│   │   │   ├── campaign_budget_optimization.html
│   │   │   ├── home.html
│   │   │   ├── internal_job_posting.html
│   │   │   ├── trainings.html
│   │   │   ├── volunteer_resume_analysitation.html
│   │   │   └── volunteers.html
│   │   ├── volunteer
│   │   │   ├── base.html
│   │   │   ├── cv.html
│   │   │   ├── home.html
│   │   │   ├── opportunities.html
│   │   │   ├── profile.html
│   │   │   └── trainings.html
└── test.json
```

## Installation

To set up the project locally, follow these steps:

1. **Clone the repository:**

   ```sh
   git clone https://github.com/CivicCircle/FrontEnd.git
   cd FrontEnd
   ```

2. **Create a virtual environment:**

   ```sh
   python -m venv venv
   ```

3. **Activate the virtual environment:**

   - **Windows:**
     ```sh
     venv\Scripts\activate
     ```
   - **Linux/MacOS:**
     ```sh
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

## Configuration

Ensure you have the backend server running and properly configured. Update the `app.py` file with the correct backend URLs if necessary.

## Running the Server

To start the Flask server, run:

```sh
flask run
```

The server will run on the default port `5000`. You can access the frontend at `http://localhost:5000`.

## Usage

The frontend provides an interface for managing organizations, volunteers, trainings, and opportunities. It interacts with the backend services to fetch and update data.

## Routes

### Organization Routes

- **Organization Home**

  - **Endpoint:** `/organization`
  - **Method:** `GET`
  - **Description:** Displays the organization home page.

- **Trainings**

  - **Endpoint:** `/organization/trainings`
  - **Method:** `GET`
  - **Description:** Displays all training opportunities.

- **Create Training**

  - **Endpoint:** `/organization/trainings/create`
  - **Method:** `POST`
  - **Description:** Handles the creation of a new training.

- **Update Training**

  - **Endpoint:** `/organization/trainings/update/<string:trainingID>`
  - **Method:** `POST`
  - **Description:** Handles the update of an existing training.

- **Delete Training**

  - **Endpoint:** `/organization/trainings/delete/<string:trainingID>`
  - **Method:** `POST`
  - **Description:** Handles the deletion of a training.

- **Volunteer Opportunities**
  - **Endpoint:** `/organization/volunteers`
  - **Method:** `GET`, `POST`
  - **Description:** Displays all volunteer opportunities or handles the creation of a new opportunity.

### Volunteer Routes

- **Volunteer Profile**

  - **Endpoint:** `/volunteer/profile`
  - **Method:** `GET`
  - **Description:** Displays the volunteer profile.

- **Trainings**

  - **Endpoint:** `/volunteer/trainings`
  - **Method:** `GET`
  - **Description:** Displays all training opportunities for volunteers.

- **Apply for Training**

  - **Endpoint:** `/volunteer/trainings/apply/<string:trainingID>`
  - **Method:** `POST`
  - **Description:** Handles the application for a training.

- **Volunteer Opportunities**

  - **Endpoint:** `/volunteer/opportunities`
  - **Method:** `GET`
  - **Description:** Displays all volunteer opportunities for volunteers.

- **Apply for Opportunity**
  - **Endpoint:** `/volunteer/opportunities/apply/<string:opportunityID>`
  - **Method:** `POST`
  - **Description:** Handles the application for a volunteer opportunity.

### Authentication Routes

- **Login**

  - **Endpoint:** `/auth`
  - **Method:** `GET`, `POST`
  - **Description:** Displays the login page and handles user authentication.

- **Logout**
  - **Endpoint:** `/organization/logout`
  - **Method:** `GET`
  - **Description:** Logs out the user.

## Templates

The HTML templates are located in the `server/templates` directory. These templates use Jinja2 syntax for dynamic content rendering.

- **Base Template:** `

base.html`

- **Organization Home Template:** `organization/home.html`
- **Trainings Template:** `organization/trainings.html`
- **Volunteer Opportunities Template:** `organization/volunteers.html`
- **Volunteer Profile Template:** `volunteer/profile.html`

## Static Files

Static files (CSS, JS, images) are located in the `server/static` directory. The project uses both Bootstrap and Tailwind CSS for styling.

- **CSS Files:** `server/static/styles/`
- **JavaScript Files:** `server/static/scripts/`
- **Images:** `server/static/images/`

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
