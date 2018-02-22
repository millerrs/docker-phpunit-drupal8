# PHPUnit for Drupal 8
A PHPUnit image with SQLite for running Drupal 8 Unit and Kernel tests.

## Usage

```bash
docker run -it --rm /path/to/tests:/app millerrs/phpunit-drupal8
```

or

```bash
docker run -it --rm -v /path/to/project:/app millerrs/phpunit-drupal8 phpunit -c path/to/custom/config path/to/tests
```

## Usage in Jenkins Pipeline

```groovy
stage('Run Unit Tests') {
    agent {
        docker {
            image 'millerrs/phpunit-drupal8'
        }
    }
    steps {
        sh 'phpunit -c web/core web/modules/custom'
    }
}
```