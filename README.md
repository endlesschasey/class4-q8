# 第四课作业

## Question 8: 

为枚举交通信号灯实现一个 trait，trait里包含一个返回时间的方法，不同的灯持续的时间不同

```rust
trait TrafficLight {
    fn duration(&self) -> u32;
}

enum Light {
    Red,
    Yellow,
    Green,
}

impl TrafficLight for Light {
    fn duration(&self) -> u32 {
        match self {
            Light::Red => 60,
            Light::Yellow => 10,
            Light::Green => 50,
        }
    }
}

fn main() {
    let red_light = Light::Red;
    let yellow_light = Light::Yellow;
    let green_light = Light::Green;

    println!("红灯持续时间: {} 秒", red_light.duration());
    println!("黄灯持续时间: {} 秒", yellow_light.duration());
    println!("绿灯持续时间: {} 秒", green_light.duration());
}
```