# Contributing to CareConnect

Thank you for your interest in contributing to CareConnect! This document provides guidelines and instructions for contributing.

## 🤝 How to Contribute

### Reporting Bugs
1. Check if the bug has already been reported
2. Use the bug report template
3. Include detailed steps to reproduce
4. Add screenshots if applicable
5. Specify your environment (OS, browser, Node version)

### Suggesting Features
1. Check existing feature requests
2. Clearly describe the feature
3. Explain the use case
4. Consider implementation details

### Code Contributions

#### Getting Started
1. Fork the repository
2. Clone your fork
3. Create a feature branch
4. Make your changes
5. Test thoroughly
6. Submit a pull request

#### Branch Naming
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation
- `refactor/` - Code refactoring
- `test/` - Test additions

Example: `feature/add-appointment-reminders`

## 💻 Development Guidelines

### Code Style
- Use ESLint configuration
- Follow React best practices
- Use functional components with hooks
- Keep components small and focused
- Write meaningful variable names

### Component Structure
```jsx
// Imports
import { useState } from 'react'
import { Button } from '@/components/ui/button'

// Component
export default function MyComponent({ prop1, prop2 }) {
  // State
  const [state, setState] = useState(null)
  
  // Effects
  useEffect(() => {
    // Effect logic
  }, [])
  
  // Handlers
  const handleClick = () => {
    // Handler logic
  }
  
  // Render
  return (
    <div>
      {/* JSX */}
    </div>
  )
}
```

### File Naming
- Components: PascalCase (e.g., `UserProfile.jsx`)
- Utilities: camelCase (e.g., `formatDate.js`)
- Constants: UPPER_SNAKE_CASE (e.g., `API_ENDPOINTS.js`)

### Commit Messages
Follow conventional commits:
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation
- `style:` - Formatting
- `refactor:` - Code restructuring
- `test:` - Adding tests
- `chore:` - Maintenance

Example: `feat: add appointment reminder notifications`

## 🧪 Testing

### Before Submitting PR
- [ ] Code runs without errors
- [ ] All features work as expected
- [ ] Responsive on mobile/tablet/desktop
- [ ] No console errors or warnings
- [ ] ESLint passes
- [ ] Documentation updated

### Manual Testing
Test your changes across:
- Different user roles
- Different browsers
- Different screen sizes
- Edge cases

## 📝 Pull Request Process

1. **Update Documentation**
   - Update README if needed
   - Add comments to complex code
   - Update CHANGELOG

2. **Create PR**
   - Use descriptive title
   - Fill out PR template
   - Link related issues
   - Add screenshots for UI changes

3. **Code Review**
   - Address reviewer feedback
   - Keep PR focused and small
   - Respond to comments promptly

4. **Merge**
   - Squash commits if needed
   - Delete branch after merge

## 🏗️ Project Structure

```
src/
├── components/     # Reusable components
├── pages/         # Page components
├── lib/           # Utilities and helpers
├── hooks/         # Custom React hooks
└── assets/        # Images, fonts, etc.
```

## 🎨 Design Guidelines

### UI/UX Principles
- Keep it simple and intuitive
- Maintain consistency
- Ensure accessibility
- Follow mobile-first approach
- Use existing components

### Color Usage
- Primary: Actions and links
- Secondary: Less important actions
- Destructive: Dangerous actions
- Muted: Disabled or secondary text

### Spacing
- Use Tailwind spacing scale
- Maintain consistent padding/margins
- Follow 8px grid system

## 🔒 Security Guidelines

### HIPAA Compliance
- Never log PHI (Protected Health Information)
- Use encryption for sensitive data
- Implement proper access controls
- Add audit logging for PHI access

### Best Practices
- Validate all user input
- Sanitize data before display
- Use parameterized queries
- Implement rate limiting
- Follow principle of least privilege

## 📚 Documentation

### Code Comments
```javascript
// Good: Explains why
// Calculate appointment duration including buffer time
const duration = baseTime + bufferTime

// Bad: States the obvious
// Add two numbers
const sum = a + b
```

### Component Documentation
```jsx
/**
 * AppointmentCard - Displays appointment information
 * 
 * @param {Object} appointment - Appointment data
 * @param {Function} onCancel - Cancel callback
 * @param {Function} onReschedule - Reschedule callback
 */
export default function AppointmentCard({ appointment, onCancel, onReschedule }) {
  // Component code
}
```

## 🐛 Debugging

### Common Issues
1. **Build Errors**: Clear cache, reinstall dependencies
2. **Auth Issues**: Check Supabase configuration
3. **Styling Issues**: Verify Tailwind classes
4. **State Issues**: Check React DevTools

### Debug Tools
- React DevTools
- Browser DevTools
- Supabase Dashboard
- Network tab for API calls

## 📦 Dependencies

### Adding New Dependencies
1. Check if really needed
2. Verify license compatibility
3. Check bundle size impact
4. Update package.json
5. Document in PR

### Updating Dependencies
- Test thoroughly after updates
- Check for breaking changes
- Update documentation if needed

## 🌍 Internationalization

When adding text:
- Use clear, concise language
- Avoid jargon
- Consider future i18n support
- Use proper grammar

## ♿ Accessibility

### Requirements
- Semantic HTML
- ARIA labels where needed
- Keyboard navigation
- Screen reader compatible
- Sufficient color contrast

### Testing
- Test with keyboard only
- Use screen reader
- Check color contrast
- Verify focus indicators

## 📊 Performance

### Best Practices
- Lazy load components
- Optimize images
- Minimize bundle size
- Use React.memo for expensive components
- Avoid unnecessary re-renders

## 🚀 Deployment

Contributors don't typically deploy, but:
- Test production build locally
- Ensure environment variables documented
- Update deployment docs if needed

## 📞 Getting Help

- 💬 Join our Discord/Slack
- 📧 Email: dev@careconnect.com
- 📖 Check documentation
- 🐛 Search existing issues

## 🎯 Priority Areas

We especially welcome contributions in:
- [ ] Test coverage
- [ ] Documentation improvements
- [ ] Accessibility enhancements
- [ ] Performance optimizations
- [ ] Bug fixes
- [ ] UI/UX improvements

## 📜 Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Give constructive feedback
- Focus on the code, not the person
- Help others learn

## 🏆 Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Credited in documentation

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to CareConnect! 🎉
