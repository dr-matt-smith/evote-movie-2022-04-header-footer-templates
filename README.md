# evote-movie-2022-04-header-footer-templates


part of the evote-2022 project sequence

- [https://github.com/dr-matt-smith/evote-movie-2022](https://github.com/dr-matt-smith/evote-movie-2022)


## NOTES for this project step


Separate header and foot page content in part-page templates that can be re-used

- create `/templates/_header.php` containing the common HTML page header and nav content, and using text in variable `$pageTitle` for the HTML title text

    ```php
    <!doctype html>
    <html lang="en">
    <head>
        <title>EVOTE MOVIE - <?= $pageTitle ?></title>
        <meta charset="utf-8">
        <style>
            @import "/css/basic.css";
            @import "/css/nav.css";
            @import "/css/footer.css";
        </style>
    </head>
    <body>
    
    <header>
        <img src="/images/logo.gif" alt="logo">
    </header>
    
    <nav>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
    
            <li>
                <a href="/?action=about" class="current_page">About Us</a>
            </li>
    
            <li>
                <a href="/?action=list">Movie ratings</a>
            </li>
    
            <li>
                <a href="/?action=contact">Contact Us</a>
            </li>
    
            <li>
                <a href="/?action=sitemap">Site Map</a>
            </li>
        </ul>
    </nav>
    ```

- create `/templates/_footer.php` containing the common HTML footer content
    
    ```php
    <footer>
        2022 &copy; A Matt Smith productions international enterprises limited production
    </footer>
    
    </body>
    </html>
    ```

- update each page to remove duplicated code, set a `$pageTitle` variable, and require-in the header and footer templates

    - for example, template page `/templates/about.php` now contains:
            
        ```php
        <?php
        $pageTitle = "about page";
        require_once __DIR__ . '/_header.php';
        //---------------- footer ---------------
        ?>
        
        <h1>
            About us
        </h1>
        
        <p>
            We are EvoteMovie MGW
        </p>
        <p>
            We are based in Dublin.
        </p>
        <p>
            We were established in 2007.
        </p>
        <p>
            We sell computers and computer services - and host this great movie voting site!.
        </p>
        
        <?php
        //---------------- footer ---------------
        require_once __DIR__ . '/_footer.php';
        ?>
        ```

