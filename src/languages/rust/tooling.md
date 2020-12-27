# Software Engineering Notes

### Rust Tooling

Improve Tests using a Single Common Client:
    
    $ cargo add lazy_static --dev

Code example for Rocket:

    use crate::lazy_static::lazy_static;

    use rocket::local::Client;
    use rocket_tut::rocket_builder;

    pub fn setup () -> &'static Client {
        lazy_static! {
            static ref CLIENT: Client = Client::new(rocket_builder()).expect("Valid Rocket instance");
        }
        &*CLIENT
    }
    