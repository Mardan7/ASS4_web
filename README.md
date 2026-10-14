# Assignment #4: Forms and Validation

This project demonstrates simple HTML forms, HTML5 validation, and Bootstrap form styling without JavaScript.

**Student:** Mardan Khalilov

**Group:** SE-2527

**Repository:** https://github.com/Mardan7/ASS4_web

## Pages

- `index.html`: student details and links to all tasks.
- `task0.html`: contact form with name, email, message, and labels.
- `task1.html`: built-in HTML5 validation using `required`, `type="email"`, and `maxlength`.
- `task2.html`: Bootstrap contact form with responsive columns, placeholders, and helper text.
- `task3.html`: interactive validity feedback and separate fixed `is-valid` / `is-invalid` examples.
- `task4.html`: responsive registration form, radio buttons, checkboxes, country selector, and reset button.
- `style.css`: shared layout and radio-group feedback styles.

## Technologies

- HTML
- CSS
- Bootstrap 5.3 (CDN)

An internet connection is needed to load Bootstrap. No JavaScript or build tools are required.

## How validation works

The browser blocks submission when required fields are empty, an email is malformed, or a typed password has fewer than 8 characters. `maxlength` limits text entry.

Tasks 3 and 4 use the `interactive-validation` class with CSS `:user-valid` and `:user-invalid`. Fields start neutral. After editing a field and leaving it, valid values get green borders and success messages; invalid values get red borders and error messages. Submitting also reveals errors in untouched required fields. The browser controls the exact timing of these interaction states. Native browser validation remains enabled (there is no `novalidate`). Feedback is linked to controls with `aria-describedby`.

Task 3 also has two read-only examples of `is-valid` and `is-invalid` inside a collapsed details section. These classes specify a fixed visual state; they do not perform validation. The editable form uses native user-interaction validity states instead.

The gender feedback uses CSS `:has()` to check the radio group's interaction state. Use a current browser for `:has()`, `:user-valid`, and `:user-invalid`.

**Password confirmation limitation:** HTML/CSS cannot compare the values of two inputs. Both password fields check the required value and 8–128 character length only. Matching values would require JavaScript or backend validation.

**Demo submission:** These static pages have no backend. A valid form uses the browser's default GET submission to reload the current page with named fields in the URL; it does not send a message or create an account. The password inputs intentionally have no `name` attribute, so passwords are excluded from the URL. Use sample data when testing.

## Manual checks for the defense

1. Open each page from the navbar and check the active link.
2. Task 0: check that clicking a label focuses its field and that the email input rejects malformed nonempty email text.
3. Task 1: submit empty fields, then try `not-an-email`, then `student@example.com`. Try typing past the name/message length limits.
4. Task 2: resize the browser; name and email stack on small screens and share a row from the Bootstrap `md` breakpoint.
5. Task 3: confirm fields are neutral on opening. Enter `not-an-email` and move to the next field: the email becomes red. Correct it to `student@example.com` and leave the field: it becomes green. Submit an empty form to reveal required-field errors. Open the details section to inspect the fixed Bootstrap examples.
6. Task 4: leave country and gender empty, then select them. Type a 7-character password and try submitting; repeat with at least 8 characters in both password fields. Different passwords of sufficient length are accepted in this no-JavaScript demo.
7. Select multiple hobbies, click Reset, and check that text, passwords, country, radios, and checkboxes return to their initial state. Fields return to their neutral appearance and feedback is hidden.
8. At a narrow mobile width, check that navigation wraps and there is no horizontal scrolling.

## Run locally

1. Download or clone the project.
2. Open the project folder in VS Code.
3. Open `index.html` in a browser. You can also use the VS Code Live Server extension.

## Publish with GitHub Pages

1. Create a GitHub repository and upload these project files.
2. Open the repository's **Settings** page.
3. Select **Pages** in the sidebar.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and the `/ (root)` folder, then save.
6. Open the published URL shown on the Pages settings screen.

For this repository the expected URL is `https://mardan7.github.io/ASS4_web/` after Pages is enabled. Publication is not verified by these source files; confirm the actual URL in repository settings and test it before submitting.

## Reference

[Bootstrap 5.3 form validation documentation](https://getbootstrap.com/docs/5.3/forms/validation/)

[MDN: :user-invalid](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-invalid) and [MDN: :user-valid](https://developer.mozilla.org/en-US/docs/Web/CSS/:user-valid)
