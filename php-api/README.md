# Apigility API Docker image #

### Enable AMQP (RabbitMQ) ###

    php composer.phar require prolic/humus-supervisor-module:dev-master
    php composer.phar require prolic/humus-amqp-module:dev-master
    php composer.phar require --dev prolic/humus-amqp-demo-module:dev-master

### Add module config ###

    'humus_amqp_module' => array(
        'default_connection' => 'default',
        'connections' => array(
            'default' => array(
                'host' => getenv('QUEUE_PORT_5672_TCP_ADDR'),
                'port' => getenv('QUEUE_PORT_5672_TCP_PORT'),
                'login' => 'guest',
                'password' => 'guest',
                'vhost' => '/',
                'persistent' => true,
            )
        )
    )

