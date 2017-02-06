# CS630 on Qemu(a virtual machine) in Ubuntu

- Author: Wu Zhangjin/falcon <wuzhangjin@gmail.com>
- Update: 2008-09-16, 2014/03/16

## Prepare

If you want to do the following exercise, PLEASE install qemu and some other
relative tools in Ubuntu/Linux system.

```
$ sudo apt-get install qemu
```

If want to do the exercise of CS630 in ubuntu with qemu, you need to execute
the following command to mirror the resources in the course site to res/:

```
$ make update
```

## Usage

### "real mode" exercise

- helloworld

```
$ ./configure src/helloworld.s
$ make
$ make boot
```

- rtc

$ ./configure src/rtc.s
$ make
$ make boot

### "protected mode" exercise

- helloworld

```
$ ./configure src/pmhello.s
$ make
$ make pmboot
```

- rtc

```
$ ./configure src/pmrtc.s
$ make
$ make pmboot
```

## NOTE

In fact, some exercise not about "protected mode" also need to use the
2nd method to compile, for they begin execution with CS:IP = 1000:0002, and
need a "bootloader" to load them, or their SIZE are more than 512 bytes, can
not be put in the first 512bytes of the disk(MBR).

See more notes from NOTE.md.
