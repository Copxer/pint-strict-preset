# 🧼 Laravel Pint Code Style Configuration

This project uses **[Laravel Pint](https://laravel.com/docs/pint)** as the PHP code style fixer to maintain clean, consistent, and modern code formatting across the application. Pint is built on top of PHP-CS-Fixer and follows Laravel's opinionated code style guide by default, with additional strict rules applied for enhanced quality and maintainability.

---

## ⚙️ Configuration

Pint strict preset is an insanely defensive coding style preset for those who demand meticulous precision in their projects. To use it, simply create a `pint.json` file with the following contents:

```json
{
    "preset": "laravel",
    "notPath": ["app/Http/Controllers/Controller.php"],
    "rules": {
        "array_push": true,
        "backtick_to_shell_exec": true,
        "date_time_immutable": true,
        "declare_strict_types": true,
        "lowercase_keywords": true,
        "lowercase_static_reference": true,
        "final_class": true,
        "final_internal_class": true,
        "final_public_method_for_abstract_class": true,
        "fully_qualified_strict_types": true,
        "global_namespace_import": {
            "import_classes": true,
            "import_constants": true,
            "import_functions": true
        },
        "mb_str_functions": true,
        "modernize_types_casting": true,
        "new_with_parentheses": false,
        "no_superfluous_elseif": true,
        "no_useless_else": true,
        "no_multiple_statements_per_line": true,
        "ordered_class_elements": {
            "order": [
                "use_trait",
                "case",
                "constant",
                "constant_public",
                "constant_protected",
                "constant_private",
                "property_public",
                "property_protected",
                "property_private",
                "construct",
                "destruct",
                "magic",
                "phpunit",
                "method_abstract",
                "method_public_static",
                "method_public",
                "method_protected_static",
                "method_protected",
                "method_private_static",
                "method_private"
            ],
            "sort_algorithm": "none"
        },
        "ordered_interfaces": true,
        "ordered_traits": true,
        "protected_to_private": true,
        "self_accessor": true,
        "self_static_accessor": true,
        "strict_comparison": true,
        "visibility_required": true
    }
}

## 📌 Notable Customizations
notPath: Excludes app/Http/Controllers/Controller.php from formatting to avoid final_class rule conflicts.

final_class: Enforces the use of final keyword on classes for immutability unless specifically excluded.

declare_strict_types: Ensures strict typing on all PHP files to avoid type coercion issues.

ordered_class_elements: Enforces consistent structure and ordering of class members for better readability.

mb_str_functions: Uses multibyte-safe string functions to ensure UTF-8 compatibility.

strict_comparison: Enforces the use of === and !== for more reliable comparisons.

Includes several other modern best practices like avoiding unnecessary else blocks and using modern type casting.

## 💡 Auto-Format on Save (VSCode)
To auto-format PHP files with Pint on every save:

Install the VSCode extension: emeraldwalk.runonsave

Add this to your VSCode settings.json:

```json
"emeraldwalk.runonsave": {
    "commands": [
        {
            "match": "\\.php$",
            "cmd": "vendor/bin/pint ${file}"
        }
    ]
}
```
This will automatically run Pint on the currently saved PHP file.
