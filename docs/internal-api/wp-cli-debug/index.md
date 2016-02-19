---
layout: default
title: WP_CLI::debug()
---

<a href="/docs/internal-api/">Internal API</a> &raquo; Output

## WP_CLI::debug()

Display debug message prefixed with &quot;Debug: &quot; when `--debug` is used.

***

### Usage

    WP_CLI::debug( $message )

<div>
<strong>$message</strong> (string) Message to write to STDERR.<br />
<strong>@return</strong> (null) <br /></p>
</div>


***

### Notes

Debug message is written to STDERR, and includes script execution time.

Helpful for optionally showing greater detail when needed. Used throughout
WP-CLI bootstrap process for easier debugging and profiling.


    # Called in `WP_CLI\Runner::set_wp_root()`.
    private static function set_wp_root( $path ) {
        define( 'ABSPATH', rtrim( $path, '/' ) . '/' );
        WP_CLI::debug( 'ABSPATH defined: ' . ABSPATH );
        $_SERVER['DOCUMENT_ROOT'] = realpath( $path );
    }
    
    # Debug details only appear when `--debug` is used.
    # $ wp --debug
    # [...]
    # Debug: ABSPATH defined: /srv/www/wordpress-develop.dev/src/ (0.225s)
    



***

### Related

<ul>



<li><strong><a href="/docs/internal-api/wp-cli-utils-format-items/">WP_CLI\Utils\format_items()</a></strong> - Render a collection of items as an ASCII table, JSON, CSV, YAML, list of ids, or count.</li>


<li><strong><a href="/docs/internal-api/wp-cli-line/">WP_CLI::line()</a></strong> - Display informational message without prefix, and ignore `--quiet`.</li>


<li><strong><a href="/docs/internal-api/wp-cli-log/">WP_CLI::log()</a></strong> - Display informational message without prefix.</li>


<li><strong><a href="/docs/internal-api/wp-cli-success/">WP_CLI::success()</a></strong> - Display success message prefixed with &quot;Success: &quot;.</li>


<li><strong><a href="/docs/internal-api/wp-cli-warning/">WP_CLI::warning()</a></strong> - Display warning message prefixed with &quot;Warning: &quot;.</li>


<li><strong><a href="/docs/internal-api/wp-cli-error/">WP_CLI::error()</a></strong> - Display error message prefixed with &quot;Error: &quot; and exit script.</li>



</ul>

