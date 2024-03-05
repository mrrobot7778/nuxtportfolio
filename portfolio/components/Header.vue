<template>
    <header class="container py-4">
        <nav>
           <ul class="d-flex justify-content-between nav nav-pills nav-one">
             <li>        
                <NuxtLink to="/subscribe" class="nav-link">Subscribe</NuxtLink>
             </li>
             <li>
                <NuxtLink to="/" class="nav-link blog-header-logo">Logo</NuxtLink>
             </li>
             <li>
                <NuxtLink to="/signup" class="nav-link sign-up">Sign Up</NuxtLink>
             </li>
           </ul>
        </nav>
        <nav>
        <ul class="d-flex justify-content-center nav nav-pills nav-two">
            <li>
                <NuxtLink to="/world" class="nav-link">World</NuxtLink> 
            </li>
            <li>
                <NuxtLink to="/politics" class="nav-link">Politics</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/science" class="nav-link">Science</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/travel" class="nav-link">Travel</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/" class="nav-link">Home</NuxtLink>
            </li>
         </ul>
       </nav>
    </header>
</template>

<style>
    

    .form-control-dark {
    border-color: var(--bs-gray);
    }
    .form-control-dark:focus {
    border-color: #fff;
    box-shadow: 0 0 0 .25rem rgba(255, 255, 255, .25);
    }

    .text-small {
    font-size: 85%;
    }

    .dropdown-toggle {
    outline: 0;
    }
    .nav-one {
        border-bottom:0.5px solid #EEEEEE;
        background: #F9F9F9;
    }
</style>