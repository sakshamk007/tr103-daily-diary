# Day 12

## Created auth.ejs layout 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AuctionBay</title>
    <link href="/src/input.css" type="text/css" rel="stylesheet">
    <link href="/src/output.css" type="text/css" rel="stylesheet">
    <!-- <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet"> -->
</head>
<body class="font-body_font">
    <div class="absolute inset-0 -z-10 h-full w-full flex justify-center items-center px-5 py-24 [background:radial-gradient(125%_125%_at_50%_10%,#000_40%,#63e_100%)]">
        <div class="lg:w-[500px] w-[350px] h-fit bg-gray-500 bg-opacity-20 rounded-2xl px-6 py-10 text-white flex justify-center items-center">
            
            <% if (page === 'signup') { %>
                <%- include('../partials/signup') %>
            <% } else if (page === 'signin') { %>
                <%- include('../partials/signin') %>
            <% } else if (page === 'profile') { %>
                <%- include('../partials/profile') %>
            <% } else if (page === 'error') { %>
                <%- include('../partials/error', {status: status, message: message}) %>
            <% } else if (page === 'success') { %>
                <%- include('../partials/success', {status: status, message: message}) %>
            <% } %> 

        </div>
    </div>

    <script>
        let elements = document.getElementsByClassName('visibility');
        Array.from(elements).forEach(element => {
            element.addEventListener('click', (e) => {
                let password = e.target.parentElement.querySelector('.password');
                if (e.target.src.includes('/img/invisible.svg')) {
                    e.target.src = '/img/visible.svg';
                    password.type = 'text';
                } else {
                    e.target.src = '/img/invisible.svg';
                    password.type = 'password';
                }
            });
        });
    </script>
</body>    
</html>

```