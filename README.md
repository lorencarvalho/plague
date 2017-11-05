[<img src="https://img.shields.io/pypi/v/plague.svg">](https://pypi.python.org/pypi/plague)</img>

plague
======

a simple gossipy infection network

# how to use

    import asyncio
    from plague import Node

    node_one = Node('127.0.0.1', 8080)
    node_two = Node('127.0.0.1', 8081)
    node_three = Node('127.0.0.1', 8082, contaminate=[node_one.addr, node_two.addr])

    node_one.infect(my_key="my_value")

    for node in (node_one, node_two, node_three):
        node.serve()

    loop = asyncio.get_event_loop()
    loop.run_forever()
