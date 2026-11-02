// BRIGHT SPARK ELECTRICAL SERVICES
// JavaScript functionality

document.addEventListener("DOMContentLoaded", function () {

    // 1. Smooth scrolling for navigation links
    const navigationLinks = document.querySelectorAll('nav a[href^="#"]');

    navigationLinks.forEach(function (link) {
        link.addEventListener("click", function (event) {
            const target = document.querySelector(this.getAttribute("href"));

            if (target) {
                event.preventDefault();
                target.scrollIntoView({
                    behavior: "smooth"
                });
            }
        });
    });

    // 2. Reveal sections when scrolling
    const sections = document.querySelectorAll("section");

    const observer = new IntersectionObserver(function (entries) {
        entries.forEach(function (entry) {
            if (entry.isIntersecting) {
                entry.target.classList.add("visible");
            }
        });
    }, {
        threshold: 0.1
    });

    sections.forEach(function (section) {
        observer.observe(section);
    });

    // 3. Display welcome message in the console
    console.log("Welcome to Bright Spark Electrical Services!");
// 4. Form validation
    const forms = document.querySelectorAll("form");

    forms.forEach(function (form) {

        form.addEventListener("submit", function (event) {

            if (!form.checkValidity()) {
                event.preventDefault();
                form.reportValidity();
                return;
            }

            console.log("Form validation successful!");
        });

    });
});

// CONTACT FORM EMAIL FUNCTIONALITY

const contactForm = document.getElementById("contactForm");

if (contactForm) {

    contactForm.addEventListener("submit", function(event) {

        event.preventDefault();

        if (!contactForm.checkValidity()) {
            contactForm.reportValidity();
            return;
        }

        const name = document.getElementById("name").value;
        const email = document.getElementById("email").value;
        const phone = document.getElementById("phone").value;
        const type = document.getElementById("type").value;
        const message = document.getElementById("message").value;

        const subject = encodeURIComponent(type);

        const body = encodeURIComponent(
            "Name: " + name +
            "\nEmail: " + email +
            "\nPhone: " + phone +
            "\nMessage Type: " + type +
            "\nMessage: " + message
        );

        window.location.href =
            "mailto:brihtspark@example.com?subject=" +
            subject + "&body=" + body;

    });
}

// ENQUIRY FORM FUNCTIONALITY

const enquiryForm = document.getElementById("enquiryForm");

if (enquiryForm) {

    enquiryForm.addEventListener("submit", function(event) {

        event.preventDefault();

        if (!enquiryForm.checkValidity()) {
            enquiryForm.reportValidity();
            return;
        }

        const service = document.getElementById("service").value;
        const response = document.getElementById("enquiryResponse");

        response.textContent =
            "Thank you for your enquiry! We have received your request for " +
            service + ". Our team will contact you with pricing and availability.";

        enquiryForm.reset();

    });
}

// SERVICE SEARCH FUNCTION

const serviceSearch = document.getElementById("serviceSearch");

if (serviceSearch) {

    serviceSearch.addEventListener("input", function() {

        const searchValue = serviceSearch.value.toLowerCase();

        const services = document.querySelectorAll(
            "#services .service-box"
        );

        let found = 0;

        services.forEach(function(service) {

            const matches = service.textContent
                .toLowerCase()
                .includes(searchValue);

            service.style.display = matches ? "" : "none";

            if (matches) {
                found++;
            }
        });

        document.getElementById("noResults").style.display =
            found === 0 ? "block" : "none";

    });
}