
> Copy these commands to your theme or in your active theme functions.php.

## To Delete An Option
```php
/**
 * Delete an option from the database.
 * Returns an error if the option didn't exist.
 * ## OPTIONS
 * <key>
 * : Key for the option.
 *
 * ## EXAMPLES
 *
 *     $ wp option delete my_option
 *     Success: Deleted 'my_option' option.
 */
$delete_option = function( $args ) {
	list( $key ) = $args;
	if ( ! delete_option( $key ) ) {
		WP_CLI::error( "Could not delete '$key' option. Does it exist?" );
	} else {
		WP_CLI::success( "Deleted '$key' option." );
	}
};
```
## To Add An Option

```php
/**
 * Add an option to the database.
 *
 * Returns an error if the option already exist.
 *
 * ## OPTIONS
 *
 * <key>
 * : Key for the option.
 * <value>
 * : value for the option.
 *
 * ## EXAMPLES
 *
 *     $ wp option add my_option value
 *     Success: Added 'my_option' option.
 */
$add_option = function( $args ) {
    list( $key, $value ) = $args;
	if ( ! add_option( $key, $value ) ) {
		WP_CLI::error( "Could not add '$key' option. Does it already exist?" );
	} else {
		WP_CLI::success( "Added '$key' option." );
	}
};
```
## To Update An Option
```php
/**
 * Update an option to the database.
 * Simple string based value
 *
 * Returns an error if the option didn't updated.
 *
 * ## OPTIONS
 *
 * <key>
 * : Key for the option.
 * <value>
 * : value for the option.
 *
 * ## EXAMPLES
 *
 *     $ wp option update my_option new-value
 *     Success: Updated 'my_option' option.
 */
$update_option = function( $args ) {
    list( $key, $value ) = $args;
	if ( ! update_option( $key, $value ) ) {
		WP_CLI::error( "Could not update '$key' option." );
	} else {
		WP_CLI::success( "Updated '$key' option." );
	}
};
```

### Add commands to `WP_CLI`
```php

if (class_exists('WP_CLI')) {
    // delete
    WP_CLI::add_command('option delete', $delete_option);

    // create
    WP_CLI::add_command('option add', $add_option);

    // update
    WP_CLI::add_command('option update', $update_option);
}

```

To extend the wp-cli properly use https://github.com/wp-cli/scaffold-package-command
