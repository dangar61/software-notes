# Software Engineering Notes

### Rust Strings

---
"Concat Strings:"
    
[Article](https://stackoverflow.com/questions/30154541/how-do-i-concatenate-strings)

    * "String and String using + operator:"

    let route: String = "/echo/".to_string();
    let param: String = "test_echo".to_string();

    let uri: String = route + &param;
    

    * "String and &str using push_str():"
    
    let mut owned_string: String = "hello ".to_owned();
    let borrowed_string: &str = "world";

    owned_string.push_str(borrowed_string);

    * "String and String using push_str():"

    let mut owned_string: String = "hello ".to_owned();
    let another_owned_string: String = "world".to_owned();

    owned_string.push_str(&another_owned_string);

    * "String and &str using + operator:"

    let owned_string: String = "hello ".to_owned();
    let borrowed_string: &str = "world";

    let new_owned_string = owned_string + borrowed_string;


---
