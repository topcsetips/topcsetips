# tracing
## GET → kernel → socket → HTTP parser → framework → handler

### Wire → NIC → Kernel (before HTTP even exists)

What arrives is:
Ethernet frame
 * → IP Packet
   * → TCP segment
     * → Encrypted TLS records (already decrypted by now)
       * → Plain bytes
**Kernel Responsibilites:**
 * NIC interrupt
 * DMA into memory
 * IP reassembly
 * TCP reassembly
 * Stream ordering
 * ACK handling

At this stage:
> The kernel has a **byte stream**, not messages.
